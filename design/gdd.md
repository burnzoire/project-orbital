# Game Design Document

## Introduction

Dust and Ice simulates a human-settled solar system (other than the Sol system) and presents the player with opportunities to solve gamified challenges as characters in the system, while progressing an overall arc for their "natural" self. 

The system operates an economy in the background which is stable without the player, but experiences ripples which the player can take advantage of. 

## Who is the player?

The player is a contractor for CogEx, a troubleshooter-for-hire whose job is to have their braincode transmitted at lightspeed across the solar system into the bodies of clients to solve whatever problems they might have while they take some time-out on a holiday server or similar. (note: there are some significant similarities to Altered Carbon here, so even though it was an original idea let's keep it differentiated). 

They have had their natural body impounded by CogEx to service a debt, which will take decades (at least) to pay off. But that body is desirable - first, it's their natural body, but also it comes with citizenship - a rare thing in this solar system where the vast majority of people are braincode-copies inhabiting vat-grown black market bodies with limited rights. 

Black market bodies (space hobos!) exist in a grey legal area where they don't have the status to visit planetside, and must exist on space stations, asteroids and outposts where their lack of identity isn't inspected closely. They do all the non-prestige, dirty, dangerous, monotonous or unpleasant jobs. 

CogEx's contract makes it clear that non-performance forfeits the body, creating a motivation to keep doing contracts - and obviously CogEx absolutely intends to never give it back to the player whatever's in the contract. So the player must find a way to escape.

While the player is solving contract problems (each of which is gameplay), they also have opportunities to set in place a social and informational network of small contacts, asset caches, little debts owed, favours, secrets, access etc (a little bit of Crusader Kings?). They are setting up to heist their own identity with a social and economic Rube Goldberg machine.

The player can cooperate with other CogEx troubleshooters to solve problems. They will also secretly collaborate with them to all escape together. 

## Game Design Principles

- You are not the chosen one
- tone is a mashup of Firefly, The Expanse, Rimworld and the Paranoia RPG. Even a bit of Oceans Eleven, if the player is setting up a long-game heist to escape CogEx and be independent again. 
- progression, but impediments to long-term progression that become increasingly difficult to overcome
- contracts are time-pressured by the client's automated braincode exchange deadline. 
- client-server, 1..n clients

## Stack

- Open, early days. Thinking is a Python+MyPy dedicated server which is somewhat client-agnostic at least in early dev. Scale from text UI to 2D sidescroller.

- conversational interaction with npcs via local llm agents. these have their own goals, motivations and gameplay abilities, items and so on that they can give to/use with the player

## Ideas

- as an overarching story, the player is looking for subtle ways they can use their contracts to set things in play for larger goals. For example: when solving a problem for (as) a CEO, they might make a small, unnoticeable hire that they can contact later for a favour. They might learn that someone is going to manipulate a stock price, and use a fake identity established on a previous contract to invest some money set aside in a different previous contract to take advantage of the manipulation. 

- The Oceans Eleven thing would be a great "game over" event, where once all the pieces are in play, you have to execute your perfect plan with your crew of troubleshooters you've enlisted along the way

- what does the solar system economy simulator actually do to impact the gameplay? does it create opportunities for the player to exploit for profit while in a contract body?

- the beginning of a thought about LLM interaction. Like if there was a possible arc outcome that the player didn't achieve in a contract, the engine can interrogate the agents and ask why they didn't convince them or what they missed. That can form the basis of hints, e.g. at the end of a contract, back in your "holding cell" server: "it occurs to you that Genevieve the receptionist complimented your hat and seemed disappointed that you didn't compliment her back. You might have missed an opportunity to get Boris's commnet code there." This trains the player on the sorts of things they should be looking out for. 
# Game Design Document

## Introduction

Dust and Ice simulates a human-settled solar system (other than the Sol system) and presents the player with opportunities to solve gamified challenges as characters in the system. 

The system operates an economy in the background which is stable without the player, but experiences ripples which the player can take advantage of. 

## Who is the player?

The player is a contractor for CogEx, a troubleshooter-for-hire whose job is to have their braincode transmitted at lightspeed across the solar system into the bodies of clients to solve whatever problems they might have. (note: there are some significant similarities to Altered Carbon here, so we need to find differentiators). 

They exist in a grey legal area where they don't have the citizenship status to visit large settlements, and must exist on space stations, asteroids and outposts where their identity isn't inspected closely. 

## Game Design Principles

- You are not the chosen one
- tone is a mashup of Firefly, The Expanse, Rimworld and the Paranoia RPG
- progression, but impediments to long-term progression that become increasingly difficult to overcome
- client-server, 1..n clients

## Stack

- Open, early days. Thinking is a Python+MyPy dedicated server which is somewhat client-agnostic at least in early dev. Scale from text UI to 2D sidescroller.
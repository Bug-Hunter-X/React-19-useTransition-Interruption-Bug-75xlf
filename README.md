# React 19 useTransition Interruption Bug

This repository demonstrates a bug related to the interruption of transitions initiated by React's `useTransition` hook in version 19. When a transition is prematurely stopped (e.g., by navigating away before completion), unexpected component behavior can occur. The provided example showcases this issue and presents a potential solution.

## Bug Description
The core problem lies in how React handles state updates during interrupted transitions.  If asynchronous operations are involved within a transition, the incomplete updates might interfere with subsequent renders, causing glitches or displaying stale data. 

## How to Reproduce
Clone this repository and run the application. Initiate a transition and interrupt it before it finishes (e.g., by clicking the button and then quickly navigating to another page). Observe any unexpected behavior.

## Solution
The proposed solution involves implementing additional cleanup logic within the transition callback to ensure that any pending asynchronous operations are cancelled or appropriately handled upon interruption.  The solution file (bugSolution.js) shows how this can be accomplished using techniques such as cancellation tokens or conditional rendering based on the transition's `isPending` state.

## Technologies Used
* React 19
* JavaScript
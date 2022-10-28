Programming Assignment 2 - CS 4410
Patrick Lyons (pml84), Samuel Aberman (sa685), Max Horowitz (mgh68)

Starvation.

For both stacksbs and stackmon there is a possibility of starvation of the validate calls.
For stacksbs, validate is only released through the release_one function when there is 
nothing left to push or pop and the stack is completely full. For a continuous stream of 
pops and pushes this condition might never be met, starving out the validate call. The same 
goes for stackmon, where the logic is engrained in the push and pop release logic, where 
validate is only notified after pop is notified and when the stack is completely full — a 
condition that will not be met when an alternating stream of pops and pushes is called. 
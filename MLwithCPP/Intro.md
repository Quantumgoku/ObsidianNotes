---
created: 2026-09-11T16:58
updated: 2026-09-11T22:47
---
ML basically finding a function to model around a graph of observation
if you have any data you can create a model



main.c:
created a train array with 2 dimension 1-> input, 2-> what we expect

Parameter -> the input our function takes gpt 4 has 1 trillion param(fcking what kind of function it is)

square mean error = measure how bad a model performs. subtract expected from actual and square it
why square? -> 
1->if any error is negative square makes it positive
2->if any error is amplified i.e if any error received is minimal it will be instantly visible if we do a square
3-> finding gradient descent and derivatives of square is easy
4-> linked to variance

cost function -> a function to determine how much our model is wrong

as we know derivative will point to where the function is growing so we need to go to opposite of that direction (for cost function) to get minimum


Learning rate -> when working with derivatives it is still too long to jump around so researcher introduced a learning rate, a rate to reduce that big jump



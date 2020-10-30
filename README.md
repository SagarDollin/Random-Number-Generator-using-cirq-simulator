# Random-Number-Generator-using-cirq-simulator
Remember how a qubit in an equal superposition can collapse to either a 1 or a 0 after measuring? Well its not possible to determine what state it will collapse before actually measuring it, so we can use this property to generate truly random numbers.

So let's quickly dive into how I have designed this algorithm. But first of all some basic knowledge we need as stated below:

A qubit is in equal superposition after you apply a Hadamard gate on it, given that it was in state 0 or 1 initially.
There is no way to determine this equal superposition will collapse to 1 or a 0 before actually measuring it.
The above property can be used to generate random numbers, for example, if I want a random number between 0 and 1 , I need 1 qubit then apply a hadamard gate on it and then measure it , so the outcome I get is either 0 or 1 and there is no way to determine which outcome you will get. Now if I want a random number between 0 and 3 I take a qubit, then apply hadamard on it and then measure it and repeat the same once again. By doing this I get the possible outputs as 00,01,10,11 and there is no way to tell which one I will get for sure because all for states are in equal superposition with a probability of 1/4.
similary if I want a random number between 0 to (2^n)-1, then I do the do the same process n times and I will get a random number between the expected range. Note that this is not a psuedo random number its a true random number.

#Algorithm
      
      1. Create a circuit with 1 qubit, apply hadamard gate and then measurement.
      
      2.Run the circuit on simulator/real quantum device "n" times(i.e., repetitions = n)
      
      3.We get a result of n bits, take these n bits and convert them to a decimal equivalent.
      
      4.The Decimal equivalent is the random number between 0 to (2^n)-1

Now, coming to the source code, Im using cirq package to write the code in python.Since I don't have access to Google's real quantum device I'm running this on a simulator so the Random Number Generated is not true random number. However if I were to ruin the same code on a real quantum device it would generate a true random number. I have tested the same algorith on IBM Quantum Hardware, and it passed the test. So the True Random Number is already generated on a Quantum device. I'll leave the link to True Random Number Generator repository that was run on real Quantum Device in the extended description.

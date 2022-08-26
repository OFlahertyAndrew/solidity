<h1>Level 0 - Hello Ethernaut</h1>

<h2>Description</h2>
Hello Ethernaut is an introductory challenge meant to familiarize you with the basics of the Ethernaut CTF.<br>
This challenge uses the browser's built-in console to interact with the level contract instance you deployed.

<h2>Analytics:</h2>
- Smart contract(s) used: No<br>
- Difficulty: Easy

<h2>Solution:</h2>
<h3>Step 1)</h3> As directed by the instructions, the first step is to interact with the level instance's contract by submitting the following into the browser console:

```
await contract.info()
```

This produces the the output 'You will find what you need in info1().'

<h3>Step 2)</h3> Building off of the output from step 1, we use the provided function name with our next level instance interaction.
This is done with the following code snippet:

```
await contract.info1();
```

The output for this contract function is 'Try info2(), but with "hello" as a parameter.'


<h3>Step 3)</h3> Much like the previous two steps, we use the provided function name for the next contract interaction. <br>
This time around, however, we also pass "hello" as a parameter.

Enter the following code into the browser's console:

```
await contract.info2("hello");
```

This code produces the output 'The property infoNum holds the number of the next info method to call.'

<h3>Step 4)</h3> We now have to access the property infoNum. This is done in using the same methods for the previous steps.<br>
We simply 

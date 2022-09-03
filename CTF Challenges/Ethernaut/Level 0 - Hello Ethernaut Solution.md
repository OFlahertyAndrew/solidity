<h1>Level 0 - Hello Ethernaut</h1>

<h2>Description</h2>
Hello Ethernaut is an introductory challenge meant to familiarize you with the basics of the Ethernaut CTF.<br>
This challenge uses the browser's built-in console to interact with the level contract instance you deployed.<br>
Access the browser's console by clicking the F12 key.

<h2>Analytics:</h2>
- Smart contract(s) used: No<br>
- Difficulty: Easy

<h2>Solution:</h2>
<h3>Step 1)</h3> As directed by the instructions, the first step is to interact with the level instance's contract by submitting the following command into the browser console:

```javascript
await contract.info()

//Output: 'You will find what you need in info1().'
```

<h3>Step 2)</h3> Building off of the output from step 1, we use the provided function name with our next level instance interaction.<br>

Call ```info1()```:

```javascript
await contract.info1();
```

The output for this contract function is 'Try info2(), but with "hello" as a parameter.'


<h3>Step 3)</h3> Much like the previous two steps, we use the provided function name for the next contract interaction. <br>
This time around, however, we also pass "hello" as a parameter.

Call ```info2()``` with the parameter ```"hello"```:

```javascript
await contract.info2("hello");

//Output: 'The property infoNum holds the number of the next info method to call.'
```

<h3>Step 4)</h3> We now have to access the property infoNum. This is done in using the same methods for the previous steps.<br>

Call ```infoNum()```:

```javascript
await contract.infoNum().then(v => v.toString());

//Output: 42
//We then use this number to perform the next command.
```

```.then(v => v.toString());``` is used to format the command's output to a string, making the result easier to read.

<h3>Step 5)</h3> Proceed with the next function call by using the number 42 from the previous command's result.<br>

Call ```info42()```:

```javascript
await contract.info42();

//Output: 'theMethodName is the name of the next method.'
```

<h3>Step 6)</h3> We now call the function "theMethodName()"<br>

Call ```theMethodName()```:

```javascript
await contract.theMethodName();

//Output: 'The method name is method7123949.'
```

<h3>Step 7)</h3> Proceed with the next function call by using the method name "method7123949" from the previous command's result.<br>

Call ```method7123949()```:

```javascript
await contract.method7123949();

//Output: 'If you know the password, submit it to authenticate().'
```

<h3>Step 8)</h3> After the previous function call, we now know that we need a password to pass to the "authenticate()" function.<br>
We can peform a couple of commands to investigate further.<br>

Option 1: ```contract```:

```javascript
await contract;
```

Option 2: ```contract.abi```:

```javascript
await contract.abi;
```

In either case, the ABI of the contract is returned by the command.<br>

The output has a lot more than we need. We will focus on this specific block of text:
```javascript
{
        "inputs": [],
        "name": "password",
        "outputs": [
            {
                "internalType": "string",
                "name": "",
                "type": "string"
            }
        ],
        "stateMutability": "view",
        "type": "function",
        "constant": true,
        "signature": "0x224b610b"
    },
```

This text block describes a function called ```password```.<br>
We now call this function to get the password:

```javascript
await contract.password();

//Output: ethernaut0
```

<h3>Step 9)</h3> Now that we have the password, we pass it to the "authenticate()" function.<br>

Call ```authenticate()``` with the parameter ```"ethernaut0"```:

```javascript
await contract.authenticate("ethernaut0");
```
Now, simply submit your contract instance and you've completed the level!

<h3>Congratulations! You can view the next challenge and the instructions on how to complete it here.</h3>

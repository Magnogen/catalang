# Avoweliu
`Unimplemented` | `Shelved`

Avoweliu is an esolang I started a little while back that uses the vowels of the English alphabet, including `A`, `E`, `I`, `O`, `U`, `Y` as well as numbers - both positive and negative.

This is an example program:

```
AiA1I1O48YU1O49OI1
```

Very esoteric indeed.

---

## How it works

**First**, the interpreter splits the string into multiple commands, or lines.
It does this using a simple rule: Every command starts with a capital vowel.

So the above code would be splitted like this:

```
Ai
A1
I1
O48
Y
U1
O49
O
I1
```

If the program starts with anything but a capital vowel, there's a Syntax Error because then it wouldn't start with a command.
The only other legal characters are the numbers `0 - 9`, and a hyphen `-`.
So, if there are any consonants or other characters in the code, that's another error too. 

**Second**, the interpreter uses the first letter of the command to determine what it does. 
Kind of like a statement in regular, non-esoteric languages. 

Here's a handy little table for each of the options:

| Vowel | Action |
| - | - |
| `A` | [Manipulating the stack](#a-manipulating-the-stack) |
| `E` | [*Idk lol I didn't get this far*](#e-unfinished) |
| `I` | [Input and if conditions](#i-input-and-if-conditions) |
| `O` | [Sending outputs and performing operations](#o-sending-outputs-and-performing-operations) |
| `U` | [Upoints - the Avoweliu equivalent of GOTO](#u-upoints---the-avoweliu-equivalent-of-goto) |
| `Y` | [Ending the program or returning from a Upoint](#y-ending-the-program-or-returning-from-a-upoint) |

Stalue: Value of stack (top unless specified)<br>
Push:   Add a stalue<br>
Pop:    Remove and return stalue

### `A` Manipulating the stack
- `A`:  reverse stack
- `A#`: push #
- `A-`: remove top stalue
- `a`:  return top stalue
- `a#`: returns stalue at index
- `a-`: return length of stack

### `E` (unfinished)
- `E`:  
- `E#`: 
- `E-`: 
- `e`:  
- `e#`: 
- `e-`: 

### `I` Input and if conditions
- `I`:  prompt for input and push to input stack
- `I#`: if top 2 stalues are equal, goto upoint #
- `I-`: remove last input
- `i`:  return most recent input
- `i#`: return normalised (-#, 0, # -> -1, 0, 1)
- `i-`: pop most recent input

### `O` Sending outputs and performing operations
- `O`:  output content of buffer
- `O#`: append # to buffer
- `O-`: remove last character of buffer
- `o`:  return content of buffer
- `o#`: return operation # on top 2 stalues
- `o-`: pop last character of buffer

### `U` Upoints - the Avoweliu equivalent of GOTO
- `U`:  goto random upoint, next or last
- `U#`: goto upoint with id #
- `U-`: goto last upoint
- `u`:  goto and return random upoint
- `u#`: goto and return upoint with id
- `u-`: goto and return last upoint

### `Y` Ending the program or returning from a Upoint
- `Y`:  end program successfully or return null
- `Y#`: return value
- `Y-`: throw a runtime error

---

## Example Programs

Here are some example programs written in **Avoweliu**:

### Truth machine

Takes an input of 0 or 1, and if its a 0, outputs a 0, and if its a 1, outputs an infinite number of 1s.

```
AiA1I1O48YU1O49OI1
```
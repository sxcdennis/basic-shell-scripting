#Archive stuff
These are some materials I decided not to put in..
They wont be in any particular order so if you stumble upon this information you can try to decipher it yourself :P

<table>
  <thead>
    <tr>
      <th>Variable</th>
      <th>Function</th>
    </tr>
  </thead>
  <tbody>
<tr>
<td> $_ </td>
<td> In a script, it will execute previous character argument.</td>
</tr>
</tr>
</tbody>
</table>
<br>
## $_ :

In a script, it will execute previous character argument.

**Example:**

**Input Script:**

```
#!/bin/bash
# This will be an example of using $_
# The filename will be called lastchar.bash

echo Hello what is your name?
read a

echo Nice to meet you "$a!"

echo $_ What a wonderful name.

```

**Command Line:**

```
./lastchar.bash
```

**Output:**

```
Hello What is your name?
Stupid
Nice to meet you Stupid!
Stupid! What a wonderful name.
```

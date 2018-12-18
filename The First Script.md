# The First Script
For our first script, we'll just write a script that says "Hello World". Later, we'll make some variations
# Video:

# Hello World Script
The following is a guide to create your first "Hello World" script:

- First, create a directory for your scripts. Mine is located at /home/scripts ```#mkdir /home/scripts/```

- Go to the directory using cd. ```#cd /home/scripts```

-  Create the file and call it Helloworld1.bash ```#vi Helloworld1.bash```

- Add the following lines and then save:

```#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This script will output "Hello World"
# Date Modified: 12/13/2018

echo Hello world```

- Make sure your file is executable ```#chmod a+rx Helloworld1.bash```

- Execute the script ```#./Helloworld1.bash```

Simple right? It just outputs Hello world to you!

# Variations of Hello World
Now we dig deeper into variations of Hello World and reasoning behind each one.
Here is a script I created called <b> Helloworld2.bash:</b>

```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This script has variations of Hello World"
# Date Modified: 12/13/2018

  echo 0. Hello World
  echo 1. "Hello     World"	      
  echo 2. "Hello World"
  echo 3. "Hello * World"
  echo 4. hello * world         # YOU CAN ALSO COMMENT HERE!!!
  echo 5. "hello "big" \"*\" World"
  echo 6. "Hello" World
  echo 7. Hello "     " World
  echo 8. 'Hello' world
  echo 9. `Hello` world
```
Now go into detail on what each one outputs: <br>
<b> 0. </b> This is from the first script Hello World.<br>
<b> 1.</b> Since the text is in quotes of <b>""</b> it outputs the exact text within the quotations<br>
<b> 2. </b> This applies the same as 1.<br>
<b> 3. </b>  This applies for 1 and 2<br>
<b>4.</b>  Since <b>* </b> is a wildcard that matches anything in Unix/Linux it will produce an output of all file names located within the directory. Thus the output of ```hello filenames world```. Also take note that the comment is not shown in the output as well.<br>
<b>5.</b> Notice how the ```"big"``` doesn't have quotations whereas the ```"*"``` does. <br>
<b>6.</b> Looking back at <b>5</b> you can see that <b>big</b> was not in quotes so is <b>"Hello"</b> in this situation<br>
<b>7.</b> This looks at the quotations and takes the spacing for it as well.<br>
<b>8.</b> This has the same functionalities as <b>""</b><br>
<b>9.</b> Notice how this causes an error. The reason being is because anything withing the <b>``` `Hello` ``` </b> are meant for commands.<br>

Not bad right? All of this makes more sense later on when you look into details of scripts! Continue reading!

[ < Back: Scripting Standards ](https://github.com/sxcdennis/basic-shell-scripting/blob/master/Scripting%20Standards.md) | [ Next: Running Simple Tasks >](https://github.com/sxcdennis/basic-shell-scripting/blob/master/Running%20Simple%20Tasks.md)

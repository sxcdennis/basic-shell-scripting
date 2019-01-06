# Renaming Files

Sometimes it can be useful to rename several files. This is an example of changing file extensions from txt to php.


## Video

https://youtu.be/2UY4jhg1rJM

## Code

**renamefiles.sh**

```
#!/bin/bash
tocuh file1.txt file2.txt file3.txt
for filename in *.txt
do
mv $filename ${filename%.txt}.php
done

```

Now check to see if the files are there ```ls *.php ```

## Output

```

file1.php file2.php file3.php

```

## Summary

Although this example is pretty simple, there are many different ways you can change this script to be more complex. For example, if you wanted to rename the file and then move them to a separate location.

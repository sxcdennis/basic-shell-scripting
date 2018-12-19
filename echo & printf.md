#  echo & printf

In this section we'll talk about the use of echo and printf within bash scripting.

## echo

**echo** is probably one of the most used command for Linux bash. It inputs a line of text and displays it standard output.

```

Common Options

 -n
     Do not output the trailing newline.

 -E
     Disable the interpretation of the following backslash-escaped characters.

 -e
     Enable interpretation of the following backslash-escaped
     characters in each String:

    \a          alert (bell)

    \b          backspace

    \c          suppress trailing newline

    \e          escape

    \f          form feed

    \n          new line

    \r          carriage return

    \t          horizontal tab

    \v          vertical tab

    \\          backslash
```

## printf

```
Common options
\"     double quote

\0NNN  character with octal value NNN (0 to 3 digits)

\b     backspace

\f     form feed

\n     new line

\t     horizontal tab

%%     a single %

%b     ARGUMENT as a string with `\' escapes interpreted

%q     Output the corresponding argument in a format that can be
       reused as shell input
%f	Interpret and print the associated argument as floating point number

%s     Character string char
```
# Video:














[< Back: Running Simple Tasks](https://sxcdennis.github.io/basic-shell-scripting/Running%20Simple%20Tasks "Running Simple Tasks")
|[Next: Variables >](https://sxcdennis.github.io/basic-shell-scripting/Variables "Variables")

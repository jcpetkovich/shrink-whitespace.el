# shrink-whitespace.el

`shrink-whitespace` is a DWIM whitespace removal key for emacs. The behaviour is
pretty simple, but I haven't found anything else that does what I want.

# Usage

Consider the following scenario, point represented by (|):

```
Here is some text


(|)



Here is some more text
```

When you invoke `shrink-whitespace`, the whitespace between the lines is reduced
to a single line like so:

```
Here is some text
(|)
Here is some more text
```

If you want to remove further whitespace, just invoke it again:

```
Here is some text
(|)Here is some more text
```

Now there is no space between the two lines, and point is at the beginning of
the second line.


This same function works with horizontal space, and uses the same general logic.
Consider the following scenario:

```c
int main(int argc,     (|) char *argv[])
{

	return 0;
}
```

Invoking `shrink-whitespace` removes the extra whitespace around point:

```c
int main(int argc, (|)char *argv[])
{

	return 0;
}
```

And can be invoked again:

```c
int main(int argc,(|)char *argv[])
{

	return 0;
}
```

That's really all there is too it, but I find it remarkably useful, and use it
every single day.

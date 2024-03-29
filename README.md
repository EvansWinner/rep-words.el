# rep-words.el

 This quick little hack searches from point forward for words that
 repeat too many times within a short space of text--a common problem
 (or phenomenon, at any rate) in fiction or other writing.  Once
 found, said words are highlighted and you have the option to
 recursively edit them or skip them.  This is part of a larger project
 i am working on--called `litmus'--for working with literary
 manuscripts.  I wrote this to use with my own novel manuscript
 because i couldn't find such a thing ready-made.  I found it useful,
 so here it is.

 The entry point is the function `rep-words'.

 To use, do M-x rep-words RET.  With a prefix argument `rep-words'
 will prompt for how large an area of text should be searched
 surrounding the current word.  If you say `100' then you will be
 shown words that have too many repeats within 50 words one way or the
 other; then it will prompt for the number of repeats that in your
 view constitutes `too many'.  So you might do:

 C-u M-x rep-words RET 200 RET 3 RET -- to search for any word that is
 repeated more than 3 (4 or more) times in any 200 word stretch.

 Without a prefix argument `rep-words' will use the values of
 `rep-max-repeats' (default: 2) and `rep-region-size' (default: 100).

 Each time a match is found all occurrences of it in the buffer will
 be highlighted and you will be given the option to skip it, quit
 entirely (leaving point where it is) or recursively edit.  If you
 choose to edit, the usual C-M-c will take you back to the search, but
 starting at the CURRENT location of point, not where it was when you
 entered the edit.

 Finally, since some words are so common that they will constantly
 make matches you don't care about, the variable `rep-ignore-list'
 contains a list of strings--words you want the function to ignore.  I
 seed it below with a few of the more obvious English words.  Change
 it to anything you want.

 Uses hi-lock.el.  I think that's an Emacs 22 thing.  Maybe works with
 earlier versions.

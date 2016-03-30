# Turn on Spell Check

I use Vim for taking notes, creating documents, and writing code. I began to
notice that I was making small spelling errors, which I would immediately be 
alerted to in my email client or word processor by the red squiggly underline.

To turn on spell check simply type:

    :set spell spelllang=en_us

To disable spell check type:

    :set nospell

Now, being alerted to a mispelling is helpful but how about offering the suggested
correction? Simply hover over the mispelled word and press <code>z=</code> and Vim
will bring up a long list of alternatives.

If you would like to turn on spell check permanently just add the command to your <code>.vimrc</code>.

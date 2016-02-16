# ROT13 Decode Alias

ROT13 is a simple letter substitution cipher that replaces a letter with the letter 13 letters after it in the alphabet. ROT13 is a special case of the Caesar cipher, developed in ancient Rome.

I like participating in CTFs and completing wargames, and these puzzles can include decoding ROT13 so I added this simple alias to my machines.

To make the alias permanent add it to your bashrc file.

```bash
$ alias rot13="tr '[A-Za-z]' '[N-ZA-Mn-za-m]'"
```
Just echo your ROT13 encoded text and pipe it to your alias.

Example:

```bash
$ echo "Uryyb Jbeyq" | rot13
Hello World
```

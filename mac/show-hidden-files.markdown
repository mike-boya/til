# Show Hidden Files in Finder

I find myself searching for this command everytime I need it so I decided to document it. Normally, I am running from a terminal so I can just use
<code> ls -al </code> to see hidden files but occasionally I need to see hidden files in Finder. I created these quick aliases to do this to save me time
searching for the command.

```bash
alias showHidden='defaults write com.apple.finder AppleShowAllFiles TRUE; killall Finder'
alias hideHidden='defaults write com.apple.finder AppleShowAllFiles FALSE; killall Finder'
```

Add them to your bash profile to save yourself some time, name them what you like but I got a laugh out of hideHidden.

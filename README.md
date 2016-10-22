# aosp-osx-tips
Some tips to make AOSP modifications easier on OS X

1. If you forget to make the image for a case-insensitive file-system, you can always do so afterwards:

```
hdiutil create -fs 'Case-sensitive Journaled HFS+' -srcfolder ~/aosp aosp.dmg -verbose
```

And if you like seeing output, I suggest the -verbose flag. I get frustrated when I can't tell what something is doing. :P


2. Show progress when copying large files:

```
rsync -aPv ~/srcfolder ~/destinationfolder
```

Use it like you would cp, but you have added verbose/progress output which is really nice.

-a recursively
-P progress
-v verbose output

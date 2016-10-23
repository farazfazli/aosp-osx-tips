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

3. Install Mac OS X command line tools if you are getting errors related to missing header files:

  ```
  xcode-select --install
  ```
  
  Installing command line tools fixes these header files. If you are still having trouble, try uninstalling and reinstalling.

4. Fix "Can not find SDK 10.6 at /Developer/SDKs/MacOSX10.6.sdk" related messages:

  ```
  sudo ln -s /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.12.sdk /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.6.sdk
  ```
  Symlinking does the trick, just symlink whichever version it's complaining about to MacOSX.sdk
  Note: If you don't have any SDK in /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/ you will need to install Xcode first!

# Native-splash

## What is Native splash screen?

A splash screen is a graphical control element consisting of a window containing an image, a logo, and the current version of the software. A splash screen can appear while a program is launching. A splash page is an introduction page on a app or website.

## Flutter specific

When you open your app, there is a brief time while the native app loads Flutter. By default, during this time, the native app displays a white or black splash screen.
  To address this problem we can natively add or replace the existing splash screen. Now we have two types of splash screen that uses vector drawable as the logo:
  
  - Static Splash Screen: This type of splash screen uses vector drawable as the logo and is the first screen visible to the user when the application's launched.
  - Animated Splash Screen: This type of splash screen uses animation Animated vector drawable(**AVD**)

### Usage

**Static Splash Screen** :

<video width="320" height="240" controls>
  <source src="" type="video/mp4">
Your browser does not support the video tag.
</video>
  

## How it works
    
### Android

  - Your splash image will be resized to mdpi, hdpi, xhdpi, xxhdpi and xxxhdpi drawables.
  - An <item> tag containing a <bitmap> for your splash image drawable will be added in launch_background.xml
  - Background color will be added in colors.xml and referenced in launch_background.xml.
  - Code for full screen mode toggle will be added in styles.xml.
  - Dark mode variants are placed in drawable-night, values-night, etc. resource folders.

### IOS
  
  - Your splash image will be resized to @3x and @2x images.
  - Color and image properties will be inserted in LaunchScreen.storyboard.
  - The background color is implemented by using a single-pixel png file and stretching it to fit the screen.
  - Code for hidden status bar toggle will be added in Info.plist.

    


 

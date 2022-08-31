# Native-splash

![splash](https://user-images.githubusercontent.com/52850795/187625880-dcec5885-c6e2-44e6-a3cc-cddac79138a0.gif)

## What is Native splash screen?

A splash screen is a graphical control element consisting of a window containing an image, a logo, and the current version of the software. A splash screen can appear while a program is launching. A splash page is an introduction page on a app or website.

## Flutter specific

When you open your app, there is a brief time while the native app loads Flutter. By default, during this time, the native app displays a white or black splash screen.
  To address this problem we can natively add or replace the existing splash screen. Now we have two types of splash screen that uses vector drawable as the logo:
  
  - Static Splash Screen: This type of splash screen uses vector drawable as the logo and is the first screen visible to the user when the application's launched.
  - Animated Splash Screen: This type of splash screen uses animation Animated vector drawable(**AVD**)

### Usage

**Static Splash Screen** :

#### Setting up the package

- First import the package 'flutter_native_splash'
- Copy **flutter_native_splash: version** in the pubspec.yaml dependency section
- Customize the flutter_native_splash in pubspec.yaml or place it in a new file with a .yaml extension.

  ```
  dependencies:
    flutter:
      sdk: flutter

    cupertino_icons: ^1.0.2
    flutter_native_splash: ^2.2.8 //Add this line...

  dev_dependencies:
    flutter_test:
      sdk: flutter
  ```
  ```
  //Customize the bellow part...
  
  flutter_native_splash:
  # This package generates native code to customize Flutter's default white native splash screen
  # with background color and splash image.
  # Customize the parameters below, and run the following command in the terminal:
  # flutter pub run flutter_native_splash:create
  # To restore Flutter's default white splash screen, run the following command in the terminal:
  # flutter pub run flutter_native_splash:remove

  # color or background_image is the only required parameter.  Use color to set the background
  # of your splash screen to a solid color.  Use background_image to set the background of your
  # splash screen to a png image.  This is useful for gradients. The image will be stretch to the
  # size of the app. Only one parameter can be used, color and background_image cannot both be set.
  color: "#42a5f5"
  #background_image: "assets/background.png"

  # Optional parameters are listed below.  To enable a parameter, uncomment the line by removing
  # the leading # character.

  # The image parameter allows you to specify an image used in the splash screen.  It must be a
  # png file and should be sized for 4x pixel density.
  #image: assets/splash.png

  # The branding property allows you to specify an image used as branding in the splash screen.
  # It must be a png file. It is supported for Android, iOS and the Web.  For Android 12,
  # see the Android 12 section below.
  #branding: assets/dart.png

  # To position the branding image at the bottom of the screen you can use bottom, bottomRight,
  # and bottomLeft. The default values is bottom if not specified or specified something else.
  #branding_mode: bottom

  # The color_dark, background_image_dark, image_dark, branding_dark are parameters that set the background
  # and image when the device is in dark mode. If they are not specified, the app will use the
  # parameters from above. If the image_dark parameter is specified, color_dark or
  # background_image_dark must be specified.  color_dark and background_image_dark cannot both be
  # set.
  #color_dark: "#042a49"
  #background_image_dark: "assets/dark-background.png"
  #image_dark: assets/splash-invert.png
  #branding_dark: assets/dart_dark.png

  # Android 12 handles the splash screen differently than previous versions.  Please visit
  # https://developer.android.com/guide/topics/ui/splash-screen
  # Following are Android 12 specific parameter.
  android_12:
    # The image parameter sets the splash screen icon image.  If this parameter is not specified,
    # the app's launcher icon will be used instead.
    # Please note that the splash screen will be clipped to a circle on the center of the screen.
    # App icon with an icon background: This should be 960×960 pixels, and fit within a circle
    # 640 pixels in diameter.
    # App icon without an icon background: This should be 1152×1152 pixels, and fit within a circle
    # 768 pixels in diameter.
    #image: assets/android12splash.png

    # Splash screen background color.
    #color: "#42a5f5"

    # App icon background color.
    #icon_background_color: "#111111"

    # The branding property allows you to specify an image used as branding in the splash screen.
    #branding: assets/dart.png

    # The image_dark, color_dark, icon_background_color_dark, and branding_dark set values that
    # apply when the device is in dark mode. If they are not specified, the app will use the
    # parameters from above.
    #image_dark: assets/android12splash-invert.png
    #color_dark: "#042a49"
    #icon_background_color_dark: "#eeeeee"

  # The android, ios and web parameters can be used to disable generating a splash screen on a given
  # platform.
  #android: false
  #ios: false
  #web: false

  # Platform specific images can be specified with the following parameters, which will override
  # the respective image parameter.  You may specify all, selected, or none of these parameters:
  #image_android: assets/splash-android.png
  #image_dark_android: assets/splash-invert-android.png
  #image_ios: assets/splash-ios.png
  #image_dark_ios: assets/splash-invert-ios.png
  #image_web: assets/splash-web.png
  #image_dark_web: assets/splash-invert-web.png
  #background_image_android: "assets/background-android.png"
  #background_image_dark_android: "assets/dark-background-android.png"
  #background_image_ios: "assets/background-ios.png"
  #background_image_dark_ios: "assets/dark-background-ios.png"
  #background_image_web: "assets/background-web.png"
  #background_image_dark_web: "assets/dark-background-web.png"
  #branding_android: assets/brand-android.png
  #branding_dark_android: assets/dart_dark-android.png
  #branding_ios: assets/brand-ios.png
  #branding_dark_ios: assets/dart_dark-ios.png

  # The position of the splash image can be set with android_gravity, ios_content_mode, and
  # web_image_mode parameters.  All default to center.
  #
  # android_gravity can be one of the following Android Gravity (see
  # https://developer.android.com/reference/android/view/Gravity): bottom, center,
  # center_horizontal, center_vertical, clip_horizontal, clip_vertical, end, fill, fill_horizontal,
  # fill_vertical, left, right, start, or top.
  #android_gravity: center
  #
  # ios_content_mode can be one of the following iOS UIView.ContentMode (see
  # https://developer.apple.com/documentation/uikit/uiview/contentmode): scaleToFill,
  # scaleAspectFit, scaleAspectFill, center, top, bottom, left, right, topLeft, topRight,
  # bottomLeft, or bottomRight.
  #ios_content_mode: center
  #
  # web_image_mode can be one of the following modes: center, contain, stretch, and cover.
  #web_image_mode: center

  # The screen orientation can be set in Android with the android_screen_orientation parameter.
  # Valid parameters can be found here:
  # https://developer.android.com/guide/topics/manifest/activity-element#screen
  #android_screen_orientation: sensorLandscape

  # To hide the notification bar, use the fullscreen parameter.  Has no effect in web since web
  # has no notification bar.  Defaults to false.
  # NOTE: Unlike Android, iOS will not automatically show the notification bar when the app loads.
  #       To show the notification bar, add the following code to your Flutter app:
  #       WidgetsFlutterBinding.ensureInitialized();
  #       SystemChrome.setEnabledSystemUIOverlays([SystemUiOverlay.bottom, SystemUiOverlay.top]);
  #fullscreen: true

  # If you have changed the name(s) of your info.plist file(s), you can specify the filename(s)
  # with the info_plist_files parameter.  Remove only the # characters in the three lines below,
  # do not remove any spaces:
  #info_plist_files:
  #  - 'ios/Runner/Info-Debug.plist'
  #  - 'ios/Runner/Info-Release.plist'
  
  ```
#### Run the package

  - run the following commands in the terminal
    - **flutter clean**
    - **flutter pub get**
    - **flutter pub run flutter_native_splash:create** // if customization is done in the pubspec.yaml file.<br>
    **or**
    - **flutter pub run flutter_native_splash:create --path=path/to/my/file.yaml** // if customization is done in a new file.

#### Set up app initialization (Optional)
  By default, the splash screen will be removed when Flutter has drawn the first frame. If you would like the splash screen to remain while your app initializes, you     can use the preserve() and remove() methods together. Pass the preserve() method the value returned from WidgetsFlutterBinding.ensureInitialized() to keep the splash   on screen. Later, when your app has initialized, make a call to remove() to remove the splash screen.
  
  ```
  import 'package:flutter_native_splash/flutter_native_splash.dart';

void main() {
  WidgetsBinding widgetsBinding = WidgetsFlutterBinding.ensureInitialized();
  FlutterNativeSplash.preserve(widgetsBinding: widgetsBinding);
  runApp(const MyApp());
}

// whenever your initialization is completed, remove the splash screen:
    FlutterNativeSplash.remove();
```
**Animated Splash**
  
***Android implementation***
#### Setting up the package 
  - First import the package 'Animated_native_splash'
  - Copy **flutter_native_splash: version** in the pubspec.yaml dependency section
    
    ```
     dev_dependencies:
       animated_native_splash: ^1.0.0
    ```
    
    ```
     animated_native_splash:
       jsonFile: assets/splash.json
    ```
  - run the following commands in the terminal
    - **flutter clean**
    - **flutter pub get**
    - **flutter pub run flutter_native_splash:create**

**Note: IOS implementation are to be carried out in Xcode** [Medium blog](https://medium.com/swlh/native-splash-screen-in-flutter-using-lottie-121ce2b9b0a4#id_token=eyJhbGciOiJSUzI1NiIsImtpZCI6IjQwMmYzMDViNzA1ODEzMjlmZjI4OWI1YjNhNjcyODM4MDZlY2E4OTMiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiJodHRwczovL2FjY291bnRzLmdvb2dsZS5jb20iLCJuYmYiOjE2NjE3NTMxMjAsImF1ZCI6IjIxNjI5NjAzNTgzNC1rMWs2cWUwNjBzMnRwMmEyamFtNGxqZGNtczAwc3R0Zy5hcHBzLmdvb2dsZXVzZXJjb250ZW50LmNvbSIsInN1YiI6IjExMDQ5Njg2MzUzODMxMTEwMTM0OCIsImVtYWlsIjoicmlzaGlzYXJtYWg0QGdtYWlsLmNvbSIsImVtYWlsX3ZlcmlmaWVkIjp0cnVlLCJhenAiOiIyMTYyOTYwMzU4MzQtazFrNnFlMDYwczJ0cDJhMmphbTRsamRjbXMwMHN0dGcuYXBwcy5nb29nbGV1c2VyY29udGVudC5jb20iLCJuYW1lIjoicmlzaGkgc2FybWFoIiwicGljdHVyZSI6Imh0dHBzOi8vbGgzLmdvb2dsZXVzZXJjb250ZW50LmNvbS9hLS9BRmRadWNyTW40VVllQVZ5akpvY3ZQZTRJMUNZMmVDTHNVVS1YZjBuaVlOdmpPOD1zOTYtYyIsImdpdmVuX25hbWUiOiJyaXNoaSIsImZhbWlseV9uYW1lIjoic2FybWFoIiwiaWF0IjoxNjYxNzUzNDIwLCJleHAiOjE2NjE3NTcwMjAsImp0aSI6ImZhOWVmYTNhYWIwZjY3OTRlOWM3NGViYzAyZDM1ODYwZDdiOGVmMTIifQ.Fw9ATLX9nGEXGerzTbIz2iFzhyHh9R3FsNWadSYk1qfQv9e29xS2NY4WrTklghZvMpXUPLgvSviKWKaveX3cl_8GMcFk7SjbKPETw4fany2kEXlFg2y7uC3N-3o9IVCXOi_tJyJEaakeQy8vnDxj8qXU7AcY8uBZLORjNfKmvDkFxkztKohOkGXZ9yl21pWZxq0fZCoSL9itwvTt0gPUdQwjPoBou6lIkDBoJ0LMcGy_rc3hXHa3kt2ClXHnrG5vrPxY34CSBHnosXORTeU4hBO-Jn_QxHORG9f2uDwJ0b5S1qCDX2b5Kiop5zmXpvCUCU4dJ8pky9iuK-1BWu6vLQ)<br>
**Animation file taken from lottie as json**

***IOS Implementation***

  - Firstly open the project in Xcode and go to main.storyboard.
  - Here you will find the layout editor with one screen visible. We need to add a new ViewController which will be our Splash screen. You can do that by clicking on     the + sign at the top right, a popup will appear, search for View Controller and drag it to the editor as the following screenshot shows.<br>
  ![ios1](https://user-images.githubusercontent.com/52850795/187666716-f62bb632-ca92-429b-928c-09891c906175.png)
  - When step 2 is done, you will see 2 screens. Choose the new view controller and click on attributes inspector then check is initial view controller .<br>
  ![ios2](https://user-images.githubusercontent.com/52850795/187666911-42fdfbe6-ee5b-455c-a909-ab9569b5d979.png)
  -  We need to add Lottie dependency to **/ios/podFile**.
  
    pod 'lottie-ios'
    
  - So the file looks like this
  
    ```#platform :ios, '9.0' 
       target 'Runner' do  
          use_frameworks!  
  
          pod 'lottie-ios' 
        end
    ```
  
  - Then run; (Ensure you are in ios directory, if not, run cd ios from the root of your flutter project)
    
    ```pod install```
  
  - Drag and drop the .json file under /ios/Runner/ (select the Copy items if needed option), whether you created your own or downloaded a free sample from the link       above. In this tutorial, it’s named splash_screen.json .\
  
  - With the dependency and the splash_screen.json file already added, we can create our splash view controller that will handle showing the animation and then             navigating to Flutter’s application. In /ios/Runner/, create a new swift file, call it SplashViewController . Before writing anything in the class, we should           modify AppDelegate.swift to create a FlutterEngine. If we skip this step, we will not be able to navigate to FlutterViewController after the animated splash screen     completes its animation.
  
  ```
    import UIKit
    import Flutter

    @UIApplicationMain
    @objc class AppDelegate: FlutterAppDelegate {
    
      lazy var flutterEngine = FlutterEngine(name: "MyApp")
    
      override func application(
          _ application: UIApplication,
          didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
       ) -> Bool {
          // Runs the default Dart entrypoint with a default Flutter route.
          flutterEngine.run()
          // Used to connect plugins (only if you have plugins with iOS platform code).
          GeneratedPluginRegistrant.register(with: self.flutterEngine)

          return super.application(application, didFinishLaunchingWithOptions: launchOptions)
          }
      }
```
  - So we created a FlutterEngine called MyApp (You can choose any name you want), and in application ‘s didFinishLaunchingWithOptions, we should run the engine and       register the plugins with the engine. Note that the default code isGeneratePluginRegistrant.register(with: self) . Ensure that it is registered with                   self.flutterEngine instead.
  
  - With that done, now we can prepare SplashViewController to show the animation and then navigates to Flutter’s View Controller.
  
  ```
import UIKit
import Lottie

public class SplashViewController: UIViewController {
    
    private var animationView: AnimationView?
    
    public override func viewDidAppear(_ animated: Bool) {
        animationView = .init(name: "splash_screen")
        animationView!.frame = view.bounds
        animationView!.contentMode = .scaleAspectFit
        animationView!.loopMode = .playOnce
        animationView!.animationSpeed = 1.00
        view.addSubview(animationView!)
        animationView!.play{ (finished) in
            self.startFlutterApp()
        }
    }
    
    func startFlutterApp() {
        let appDelegate = UIApplication.shared.delegate as! AppDelegate
        let flutterEngine = appDelegate.flutterEngine
        let flutterViewController =
            FlutterViewController(engine: flutterEngine, nibName: nil, bundle: nil)
        
        flutterViewController.modalPresentationStyle = .custom
        flutterViewController.modalTransitionStyle = .crossDissolve
        
        present(flutterViewController, animated: true, completion: nil)
        
    }
}
```

  - In viewDidAppear we initialise the animation view with the added splash_screen.json file. You can play around the settings such as loopMode, animationSpeed, etc.       When the animation is done, we start the flutter app.
  
  - In order to get FlutterViewController , we MUST get an instance of the FlutterEngine we created and ran at AppDelegate.swift.
  
  ```
  let appDelegate = UIApplication.shared.delegate as! AppDelegate        
  let flutterEngine = appDelegate.flutterEngine
        
  let flutterViewController = FlutterViewController(engine:    
  flutterEngine, nibName: nil, bundle: nil)
  ```
  - Then present(completion:) is used to start the view controller.
  
  - It’s time now to link the ViewController created at step 2 with the SplashViewController class. That can be done by clicking on Main.storyboard and selecting the       new ViewController, then from identity inspector choose SplashViewController as the screenshot shows;
  ![ios3](https://user-images.githubusercontent.com/52850795/187671985-bd06b746-1731-46ee-afe8-486c82712adc.png)
  
  
  - The final step is to set the main interface for Main.storyboard instead of LauncherScreen.storyboard . To achieve that, click on Runner, select General tab, under     deployment info , set Main interface to Main from the dropdown menu as the screenshot shows.
  ![ios4](https://user-images.githubusercontent.com/52850795/187672115-0ab77feb-2cf6-4622-8c30-c77f1b8a694a.png)
  
  - Build and run the app, you should be able to see the animated splash screen.
  

### Now wait for everything to finish injecting. BOOM you have your animated native splash setup 🎉
  

  
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

    


 

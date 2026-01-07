# iOSEditor_objc
This application will allow the user to test run iOS apps on a simulator app (not on actual device).  Installation of XCode is required for the simulator.  Test code examples using UIKit and SwiftUI are provided and may serve as templates for other iOS apps.  It is recommended to create a separate folder on your Desktop to hold all of the test '.swift' files and corresponding iOS apps.  The XCode sdk path is hard-coded in the source code (line 159) and may need to be changed for your system.  You will also need to set the bundleIdentifer (ie,"com.yourName.") in both -(void)createInfoPlistInBundle: and -(void)launchIOSApp to something unique for your app.  These two identifiers must match or your iOS app will not launch.

An iOS app bundle is basically a folder with an '.app' extension which contains an executable and Info.plist files.  If there is a problem creating the iOS app bundle you will likely see the simulator home screen with an app icon that has a superimposed cloud icon with a downward arrow.  This app is not runnable and usually occurs because the executable file was not created.  You may right click on the iOS app icon and select Show Package Contents to inspect the bundle files.

Steps necessary for the source code to work correctly:

1. Load Sims at startup
2. Build iOS app bundle containing executable and Info.plist files
3. Boot Simulator
4. Install iOS App
5. Launch iOS App
6. Launch Simulator

The progress of each step is printed in the log area at the bottom and will have an exit code of '0' when working correctly.

To use the app:
1. Use menu 'File/Open' to open the test '.swift' file
2. Select a simulator to use (eg, iPhone 16 Pro)
3. Hit the 'Run' button and patiently wait (takes time to run through multiple steps)

The source code may be run in XCode by creating a MacOS App with a XIB Interface and Objective-C Language.  Delete both AppDelegate files and the pre-supplied code in the main.m file. Copy/paste all of the source code into the 'main.m' file.  The SandBox must be set to OFF for the editor to work; this setting is found by clicking on the brown icon with your project's name in the left margin of the XCode window.
<img width="744" height="123" alt="sb" src="https://github.com/user-attachments/assets/2883d68c-2cf8-44fc-9bda-a926406b8792" />

The app may also be run in Terminal by using the following on the cmd-line after migrating to the source code folder: clang iOSEditor.m -fobjc-arc -framework Cocoa -o iOSEditor && ./iOSEditor

# UIKit Output:
<img width="449" height="975" alt="uik" src="https://github.com/user-attachments/assets/79606784-269c-44bd-808e-403380591396" />

# SwiftUI Output:
<img width="452" height="975" alt="sui" src="https://github.com/user-attachments/assets/e78573b2-86ce-4005-8672-8fba8083ef46" />


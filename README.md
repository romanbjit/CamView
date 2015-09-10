CAMView
===

 Android library with simple yet powerful components for using device camera in your apps.

 The library contains a set of components (views), ready to be put to your layout files in order to 
 give developer instant access to the following features:

 - Instantly display the live preview video feed from the device camera
 - Scan barcodes (using built-in ZXing decoding engine)
 - Perform your own camera live data processing

 Library automatically uses old or new (V2) Android Camera API, depending on your OS version

 The main goal of this project is to have a simple and clean components, ready to be put to an existing
 view hierarchy of any existing activity, fragment or just to a layout file like any other Android component such as
 TextView, ImageView, etc. 
 
 CAMView takes and hides all the dirty work and hacks for handling the low level routines, such as camera initialization,
 configuration, streaming, orientation changes, device and cameras compatibility, threading, etc, etc, etc.

 Simply put the appropriate view component to your layout and your app is camera-ready.


Status
===

- Current stable version: **n/a**
- Current development version: **2.0.0.DEV1-SNAPSHOT**
- Historical releases: **1.1.0** (Note, 1.x versions are not API compatible with the 2.x ones)

 Please feel free to share your bugs, feature requests and pull requests of course. Issues sections is waiting for you :)

 **Please note** - current 2.x version is under heavy development and refactoring. APIs, classes and methods may be changed at any time.


Get It
===

- Maven repository: http://maven.livotovlabs.pro/content/groups/public
- Group: eu.livotov.labs
- Artifact ID: camview

```groovy

repositories {
    ...
    maven { url 'http://maven.livotovlabs.pro/content/groups/public' }
    ...
}


compile group: "eu.livotov.labs", name: "camview", version: "x.y.z", ext: "aar" // replace x.y.z with the corresponding version number

```

Usage
===
          
 Usage is very straightforward:

 1. Add the right component to your layout.xml (either in xml or programmatically at runtiume):

  - eu.livotov.labs.android.camview.CameraLiveView - if you want to display the live stream from the camera (and optionally want to process the captured feed).
  - eu.livotov.labs.android.camview.ScannerLiveView - if your goal is to scan barcodes. ScannerLiveView is ready to use barcode scanner.


 2. Get the CameraLiveView or ScannerLiveView instance and start the desired camera:

  - *startCamera()* for the CameraLiveView or *startScanner()* for the ScannerLiveView
  - If you want to work with the specific camera, get the available cameras list **getAvailableCameras()** and pass the selected one into the **startCamera(...)** or **startScanner(...)** method.


 3. For barcodes recognition, set your barcode listener into the ScannerLiveView instance: **setScannerViewEventListener(...)**


 4. When your activity stops, do not forget to release the camera and stop all previews and working threads by calling : **stopCamera()** or **stopScanner()** on appropriate LiveCameraView or LiveScannerView instance.


Documentation
===

 More documentation will be added on release.

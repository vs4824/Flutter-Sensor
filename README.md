# Flutter Sensor


A Flutter plugin to retreive all of sensor's data. [Accelerometer, Gyroscope, Proximity]

In proximity, screen will be off if the value is true. You must add the WAKE_LOCK permission in the AndroidManifest.xml

   `<uses-permission android:name="android.permission.WAKE_LOCK" />`
   
## Usage

To use this plugin, add all_sensors as a dependency in your pubspec.yaml file.

### Example

   `// Import package
    import 'package:all_sensors/all_sensors.dart';
    // Instantiate it
    List<double> _accelerometerValues;
    List<double> _userAccelerometerValues;
    List<double> _gyroscopeValues;
    bool _proximityValues = false; 
    // Access sensors value 
    accelerometerEvents.listen((AccelerometerEvent event) {
    setState(() {
    _accelerometerValues = <double>[event.x, event.y, event.z];
    });
    })
    gyroscopeEvents.listen((GyroscopeEvent event) {
    setState(() {
    _gyroscopeValues = <double>[event.x, event.y, event.z];
    });
    })
    proximityEvents.listen((ProximityEvent event) {
    setState(() {
    // event.getValue return true or false
    _proximityValues = event.getValue();
    });
    })`

# React Native Cybersource Device Fingerprint

## Getting started

`$ yarn add https://github.com/mauriciomartinscruz/react-native-cybersource-device-fingerprint`

### Manual installation

#### iOS

1. Add pod 'RNCybersourceDeviceFingerprint', :path => '../node_modules/react-native-cybersource-device-fingerprint/ios' to your Podfile
2. Run pod install from ios folder
3. Run your project (`Cmd+R`)<

#### Android

NOTE: if you use Reactive Native 0.60+ you can autolinking, ignore this step 1.

1. Open up `android/app/src/main/java/[...]/MainApplication.java`
  - Add `import com.mauriciomartinscruz.CybersourceDeviceFingerprint.RNCybersourceDeviceFingerprintPackage;` to the imports at the top of the file
  - Add `new RNCybersourceDeviceFingerprintPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-cybersource-device-fingerprint'
  	project(':react-native-cybersource-device-fingerprint').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-cybersource-device-fingerprint/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
	dependencies {
		...
		// Cybersource FingerPring by mauriciomartinscruz
		implementation project(':react-native-cybersource-device-fingerprint')
	}
  	```


## Usage
```javascript
import RNCybersourceDeviceFingerprint from 'react-native-cybersource-device-fingerprint'

// INITIALIZE THE SDK
RNCybersourceDeviceFingerprint.configure(ORG_ID).then( () => {
	console.log('THE CYBERSOURCE INIT IS OK')
})
.catch(err => {
	console.log('THE CYBERSOURCE INIT ERROR IS ', err)
})
// getSession accepts custom attributes for session, check the Cybersource SDK documentation
// example: ['url', 'merchantId', 'customerIdUnique']
RNCybersourceDeviceFingerprint.getSessionID([]).then( (obj) => {
	console.log(`The session ID is ${obj.sessionId}`)
})
.catch(err => {
	console.log('THE CYBERSOURCE ERROR IS ', err)
})

```
  

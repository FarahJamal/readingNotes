# Application Fundamentals 

- Android is a software stack for mobile devices that includes an operating system, middleware and key applications. 
![](https://pics.esmemes.com/me-coding-in-android-studio-writing-actual-code-figuring-out-42161896.png)

* Android apps can be written using Kotlin, Java, and C++ languages.
* The Android SDK tools compile your code along with any data and resource files into an APK or an Android App Bundle.
* archive file with an .apk suffix : contains the contents of an Android app that are required at runtime and it is the file that Android-powered devices use to install the app.
* An Android App Bundle, which is an archive file with an .aab suffix : contains the contents of an Android app project including some additional metadata that is not required at runtime
* An AAB is a publishing format and is not installable on Android devices, it defers APK generation and signing to a later stage.
## Android security features:
1. The Android operating system is a multi-user Linux system in which each app is a different user.
2. the system assigns each app a unique Linux user ID (the ID is used only by the system and is unknown to the app).
3. Each process has its own virtual machine (VM), so an app's code runs in isolation from other apps.
4. every app runs in its own Linux process.

### principle of least privilege : That is, each app, by default, has access only to the components that it requires to do its work and no more.
## there are ways for an app to share data with other apps and for an app to access system services:
* It's possible to arrange for two apps to share the same Linux user ID
* An app can request permission to access device data such as the device's location, camera, and Bluetooth connection. The user has to explicitly grant these permissions.

## types of app components:
1. Activities
2. Services
3. Broadcast receivers
4. Content providers
***
## An activity :is the entry point for interacting with the user. It represents a single screen with a user interface.
## A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons.
* It is a component that runs in the background to perform long-running operations or to perform work for remote processes.
* A service does not provide a user interface. 
## A broadcast receiver : is a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements.
* A broadcast receiver is implemented as a subclass of BroadcastReceiver and each broadcast is delivered as an Intent object. 
## A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access. 
* Through the content provider, other apps can query or modify the data if the content provider allows it.
* ContactsContract.Data, to read and write information about a particular person.

## Activating components
* Three of the four component types—activities, services, and broadcast receivers—are activated by an asynchronous message called an intent
* Intents bind individual components to each other at runtime.
* An intent is created with an Intent object, which defines a message to activate either a specific component (explicit intent) or a specific type of component (implicit intent).
*  content providers are not activated by intents ,  they are activated when targeted by a request from a ContentResolver. 
* You can start an activity or give it something new to do by passing an Intent to startActivity() or startActivityForResult() (when you want the activity to return a result).

## The manifest file
* Before the Android system can start an app component, the system must know that the component exists by reading the app's manifest file, AndroidManifest.xml. Your app must declare all its components in this file, which must be at the root of the app project directory.
## Declaring components

```<?xml version="1.0" encoding="utf-8"?>
<manifest  >
    <application android:icon="@drawable/app_icon.png" >
        <activity android:name="com.example.project.ExampleActivity"
                  android:label="@string/example_label">
        </activity>
    </application>
</manifest> 
```
***
***
* You must declare all app components using the following elements:
1. <activity> elements for activities.
2. <service> elements for services.
3. <receiver> elements for broadcast receivers.
4. <provider> elements for content providers.
## Declaring component capabilities
* you can use an Intent to start activities, services, and broadcast receivers.
***
***
```<manifest >
    <application >
        <activity android:name="com.example.project.ComposeEmailActivity">
            <intent-filter>
                <action android:name="android.intent.action.SEND" />
                <data android:type="*/*" />
                <category android:name="android.intent.category.DEFAULT" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```





# cordova-plugin-jitsi-meet

Cordova plugin for jitsi meet native sdk. Works with both iOS and Android, and fixes the 64-bit binary dependency issue
with Android found in previous versions of this plugin.

---

## Update note

Permision helper added ( for android )

---

## IOS Installation

On iOS/Xcode you will need to manually specify the WebRTC and JitsiMeet frameworks manually to be embedded.

Example of how to select them
here: https://github.com/seamlink-dev/cordova-plugin-jitsi-meet/blob/master/xcode-ios-framework-embed-example.png

---

## How to use

```javascript

let room_url = 'https://meet.jit.si/room_name';

plugins.JitsiPlugin.loadURL( room_url, null, function ( data ) {
    if ( data === "CONFERENCE_WILL_LEAVE" ) {
        plugins.JitsiPlugin.destroy( function ( data ) {
            // on Destroy
            console.log( "Destroy" );
        }, function ( err ) {
            // on Error
            console.log( "Error" );
        } );
    }
}, function ( err ) {
    // on load url was not work
    console.log( "Error : ", err );
} );
```

---

## How to build for ionic

```bash
ionic cordova plugin add https://github.com/d-loki/cordova-plugin-jitsi-meet

ionic cordova plugin add cordova-plugin-compat

( for cordova permision helper )

ionic cordova build android
```

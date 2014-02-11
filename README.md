PusherMan
=========

A class that handles registration and handling of push notifications tokens in iOS.

###Installation

##### Manual Installation

Install manually by adding <code>Pusherman.{h,m}</code> to your project.

#####  Cocoa Pods

<code>pod 'PusherMan'</code>


###Use

Pusherman exists to make the registration of push notifications for iOS easy. By calling a single function, you may register for push notifcations. To get started, head over to your app delegate (or wherever you will begin the registration for push notifications) and type the following:

```objc
// Register for Push Notifications
[PusherMan registerAppForPushNotifications];
```

This will go out to apple and register you for push notifications. The callback to your app from apple will occur in the following method in your app delegate.

```objc
#pragma mark - Push Notification Tokens
- (void)application:(UIApplication*)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData*)deviceToken {
  //Save the push notification token from apple
	[PusherMan setDeviceToken:deviceToken];
}
```

And that's it! You are all registered for push notifications. When they arrive, it will trigger another app delegate method: <code>application: didReceiveRemoteNotification:</code>

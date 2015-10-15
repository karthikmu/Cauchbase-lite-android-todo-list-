Kitchen Sync Android app 
=========================
### Setup

 - Clone this repo
 - Make sure you are on the latest Android Studio in the `Stable` channel.
 - Launch Android Studio, choose 'Import Project...' and select the `android` folder.
 - Verify your environment is working by debugging the app on your Android device.

 	Note: If you are running on a Mac, the Gradle build script will automatically download 
 	Sync Gateway into your `build` folder. It will even start and stop it for you every time 
 	you debug your app!

 - Mac users: while your app is running on device, open the
   [Sync Gateway admin console](http://localhost:4985/_admin/). Feel free to look around, but we'll
   come back to this later.
 
if you a Sync Gateway please uncomment the following function call and put your server name and port
 Now let's add a call to `startSync` in our `onCreate` override:


        startSync();

        ...
```
1.  Build and run time! Shortly after launching, you should see lots of sync activity scrolling by
     in ADB's logcat window for your device. Make sure that you have some list items for
     Couchbase Lite to sync.

2.  Let's go see the results of sync in the Sync Gateway Admin Console. Open your browser to
     [http://localhost:4985/_admin/](http://localhost:4985/_admin/), and click on the
     [kitchen-sync](http://localhost:4985/_admin/db/kitchen-sync) link. You will land on the
     **Documents** page, which will list all documents found. Clicking on a document id will reveal
     the contents of the document.


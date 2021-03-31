# Service Launch App
 Sample application that will run a service on a background (**including API Level 24 or higher**).
 The application will always run on the background

## Requirements
 Android Studio Native Application using java

## Installation
 Download and import to your project
## Usage
The following example demonstrates how to open a file:
```java
/**
     * luanching the app from the background
     * */
    public void LuanchApp(String packageName){
        Intent intent = getPackageManager().getLaunchIntentForPackage(packageName);
        if (intent != null) {
            // We found the activity now start the activity
            intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
            Log.i("MyActivity", "Start APP");
            startActivity(intent);
        } else {
            // Bring user to the market or let them choose an app?
            intent = new Intent(Intent.ACTION_VIEW);
            intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
            intent.setData(Uri.parse("market://details?id=" + packageName));
            Log.i("MyActivity", "Download APP ");
            startActivity(intent);
        }
    }



```



## Notes
 * The objective of this example is to show how the background service work
 * Native Service only work using native code

## License
This project is licensed under the terms of the [MIT License](https://opensource.org/licenses/MIT).

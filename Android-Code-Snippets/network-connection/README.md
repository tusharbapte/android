## Check for network connection
How to check for network connection based on this [stackoverflow](http://stackoverflow.com/a/4009133) answer.

make sure to add the permission to `AndroidManifest.xml` :
```xml
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

then to check the network connection:
```java
// check internet
private boolean isNetworkConnected() {
    ConnectivityManager cm = (ConnectivityManager) getSystemService(Context.CONNECTIVITY_SERVICE);
    NetworkInfo ni = cm.getActiveNetworkInfo();
    if (ni == null) {
        // There are no active networks.
        return false;
    } else {
        return true;
    }
}
```
to do work based on network connection: 
```java
// if Internet is available
if (isNetworkConnected() ){
    // do some work here
}else{
    // do some work when no Internet
}
```
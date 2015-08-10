## Basic Shared Preferences
Basic shared preferences usage based on this [stackoverflow](http://stackoverflow.com/a/11027631/4576720) answer.

###### To store values in shared preferences:
```java
SharedPreferences preferences = PreferenceManager.getDefaultSharedPreferences(this);
SharedPreferences.Editor editor = preferences.edit();
String something = "Some String";
editor.putString("KEY", something);
editor.apply();
```

###### To retrieve values from shared preferences:
```java
SharedPreferences preferences = PreferenceManager.getDefaultSharedPreferences(this);
String name = preferences.getString("KEY", "");
if(!name.equalsIgnoreCase(""))
{
    name = name + "  Something else";
}
```
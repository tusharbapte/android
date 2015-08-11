## Using Custom Fonts
To use a custom font in the app, place the font file in the `assets` folder.

sample font directory:
```
.../assets/fonts/font-name.ttf
```

in your main activity define the font path and load font as follow:
```java
// path for the font
String fontTitle = "fonts/OpenSans-Regular.ttf";

// calling Typeface
Typeface titleFont = Typeface.createFromAsset(getAssets(), fontTitle);

// find the textview
TextView title = (TextView) findViewById(R.id.title);

// apply the font
title.setTypeface(titleFont);
```
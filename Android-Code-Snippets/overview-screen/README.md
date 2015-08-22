## Change overview screen on Lollipop
Change the overview screen on Lollipop (including icon, label, and top bar color)

Add the following code to `onCreate` method: 

```java
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) 
{
    TypedValue typedValue = new TypedValue();
    Resources.Theme theme = getTheme();
    theme.resolveAttribute(R.attr.colorPrimary, typedValue, true);
    int color = Color.parseColor("#EFEFEF"); // top bar color

    Bitmap bm = BitmapFactory.decodeResource(getResources(), R.drawable.ic_action); // icon
    ActivityManager.TaskDescription td = new ActivityManager.TaskDescription(null, bm, color);

    setTaskDescription(td);
    bm.recycle();
}
```
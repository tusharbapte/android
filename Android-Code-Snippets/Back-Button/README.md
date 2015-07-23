## Add back button to the action bar
Add the following to `onCreate` method:

```java
getActionBar().setDisplayHomeAsUpEnabled(true);
```

then add this in the activity which you want to add the back button: 
```java
@Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle item selection
        switch (item.getItemId()) {
            case android.R.id.home:
                // app icon in action bar clicked; goto parent activity.
                this.finish();
                return true;
            default:
                return super.onOptionsItemSelected(item);
        }
    }
```
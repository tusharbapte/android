## Remove underline from links in TextView
How to remove the underline from links in TextView based on this [stackoverflow](http://stackoverflow.com/a/4463535/4576720) answer.

```java
package com.dolatabadi.android;

import android.os.Bundle;
import android.text.Spannable;
import android.text.TextPaint;
import android.text.method.LinkMovementMethod;
import android.text.style.URLSpan;
import android.widget.TextView;

// some activity
public class SomeActivity extends BaseActivity {

    private TextView description;

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.some_activity);

        // get the textview    
        description = (TextView) findViewById(R.id.description);
        // make links clickable 
        description.setMovementMethod(LinkMovementMethod.getInstance());
        // call the function to remove the underline from links in the text view    
        stripUnderlines(description);

    }
    // remove the underline
    private void stripUnderlines(TextView description) {
        Spannable s = (Spannable)description.getText();
        URLSpan[] spans = s.getSpans(0, s.length(), URLSpan.class);
        for (URLSpan span: spans) {
            int start = s.getSpanStart(span);
            int end = s.getSpanEnd(span);
            s.removeSpan(span);
            span = new URLSpanNoUnderline(span.getURL());
            s.setSpan(span, start, end, 0);
        }
        description.setText(s);
    }
    // customized version of URLSpan 
    private class URLSpanNoUnderline extends URLSpan {
        public URLSpanNoUnderline(String url) {
            super(url);
        }
        @Override public void updateDrawState(TextPaint ds) {
            super.updateDrawState(ds);
            ds.setUnderlineText(false);
        }
    }

}


```
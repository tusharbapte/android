## Run a function after number of seconds
How to run a function after a specific number of seconds based on this [stackoverflow](http://stackoverflow.com/a/2258080) answer.

```java
new java.util.Timer().schedule( 
        new java.util.TimerTask() {
            @Override
            public void run() {
                // your function code here
            }
        }, 
        5000 
);
```
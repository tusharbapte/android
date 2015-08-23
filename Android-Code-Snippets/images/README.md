## Images / Resources related code snippets

#### How to set a bitmap from resource

```java
Bitmap bm = BitmapFactory.decodeResource(getResources(), R.drawable.image);
```

#### Crop a bitmap

```java
Bitmap cropimg; // cropped image
Bitmap bitmap = .... ; // your bitmap
cropimg = Bitmap.createBitmap(bitmap, 0, 170, bitmap.getWidth(), bitmap.getHeight()-560);

```
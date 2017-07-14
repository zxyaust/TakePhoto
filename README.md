# TakePhoto
system method to take photo or pick photo用系统方式拍摄照片或者选取照片,下方有中文说明
# how to use
## 1.download file **SystemPhotoUtil.java** in this project,then add it to you project

## 2.use it to pick or take a photo,also you can crop a picture
    you can use like this:
```
    //create a util object
    SystemPhotoUtil  photoUtil = new SystemPhotoUtil();
    //set crop size of the bitmap,default is 250*250
    photoUtil.setCropPhotoSize(250,250);
    //take photo
     photoUtil.takePhoto(activity);
     //pick photo
      photoUtil.pickPhoto(activity);
      //get the bitmap you want in the method onActivityResult in your activity
       @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        Bitmap bitmap = photoUtil.onResult(this, requestCode, resultCode, data);
        if (bitmap != null)//you must make sure it is not null
            iv_avatar.setImageBitmap(bitmap);
    }
```

# 如何使用

## 1.下载此工程中的 **SystemPhotoUtil.java**文件,并且添加到你的安卓项目里面

## 2.下面你就可以开始用他来选一张照片,或者拍摄一张照片了
    你可以这样使用:
```
    //创建一个对象
    SystemPhotoUtil  photoUtil = new SystemPhotoUtil();
    //设置你要截取的图片的大小,默认是250*250的
    photoUtil.setCropPhotoSize(250,250);
    //拍摄照片
     photoUtil.takePhoto(activity);
     //选择一张照片
      photoUtil.pickPhoto(activity);
      //你可以在 onActivityResult方法中获取到截取的bitmap对象,并使用它
       @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        Bitmap bitmap = photoUtil.onResult(this, requestCode, resultCode, data);
        if (bitmap != null)//这里必须判空
            iv_avatar.setImageBitmap(bitmap);
    }
```
thanks: http://www.cnblogs.com/changyiqiang/p/6144329.html

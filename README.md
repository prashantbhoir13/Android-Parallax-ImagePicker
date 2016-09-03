# Parallax-CameraGalleryImagePicker-

This repository for?

Parallex CameraGalaryImage Picker
Version 1.0


How do I get set up?

Gradle Set Up

repositories {
    maven {
        url  "http://dl.bintray.com/prashantbhoir13/CameraGalleryImagePicker"
    }
}

dependencies {
    compile 'com.pkb.cameralibrary:cameralibrary:1.01'
}


Add Permission

<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" /> 
<uses-permission android:name="android.permission.CAMERA" />
<uses-feature android:name="android.hardware.camera" />
<uses-feature android:name="android.hardware.camera.autofocus" />


Add Activity In Menifest

<activity android:name="com.pkb.cameralibrary.CameraGalleryImageActivity"/>


Declare Constant Variable to Code

int ACTIVITY_REQUEST_CODE=1; 
int ACTIVITY_RESULT_CODE=2;


Call To CameraGallery Picker where you want

Intent in=new Intent(getApplicationContext(),CameraGalleryImageActivity.class);
startActivityForResult(in,1);


Get Image Uri

Override protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    if(requestCode==ACTIVITY_REQUEST_CODE){
        if(resultCode==ACTIVITY_RESULT_CODE){
            Log.e("DATA RESPONCE",""+data.getExtras().getString("path"));
        }
    }
    super.onActivityResult(requestCode, resultCode, data);
}

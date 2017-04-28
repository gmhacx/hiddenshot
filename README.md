# hiddenshot
* hiddenshot is a simple library to take a screenshot programmatically on demand. 
* Screenshot is saved in the picture folder on the device. 
* Share a screenshot as image or image with text.
* Take continous screenshots periodically.

## Apps using hiddenshot,

* NewsF

https://play.google.com/store/apps/details?id=com.veer.newsblast

## Getting Started

*  Add this to build.gradle
```
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

*  Add dependency for library
```
dependencies {
	        compile 'com.github.karanvs:hiddenshot:v1.2'
	}
```

## Usage

* Permissions, needed to save and read the screenshot from the disc.

```
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"></uses-permission>
 <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"></uses-permission>
```


* Get the Screenshot as, 

```
Bitmap shot = HiddenShot.getInstance().buildShot(activity);
```

* Save the screenshot as, 

```
HiddenShot.getInstance().saveShot(MainActivity.this, shot, "view");

```
* Take and share screenshot as,

```
HiddenShot.getInstance().buildShotAndShare(MainActivity.this);

                      OR
		      
HiddenShot.getInstance().buildShotAndShare(MainActivity.this,"your share message");		      

```

* Take continous shots,

```
HiddenShot.getInstance().buildContinousShot(MainActivity.this, timeInterval); //specify your value in timeinterval 

Stop continous shot in onDestroy()

@Override protected void onDestroy() {
    HiddenShot.getInstance().stopContinousShot(); //this can be called manually to stop shots at any time
    super.onDestroy();
  }
  
```

### License

This project is licensed under the Apache 2.0 License - see the [LICENSE.txt](LICENSE.txt) file for details


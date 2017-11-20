# android-toast
just a boilerplate app for connect react-native and android native

## install 

```
npm install --save https://github.com/sarangan/android-toast.git
```


Add the following to android/settings.gradle:

```
include ':android-toast'
project(':randroid-toast').projectDir = new File(settingsDir, '../node_modules/android-toast/android')
```


Add the following to android/app/build.gradle:
```
...

dependencies {
    ...
    compile project(':android-toast')
}
```


Add the following to android/app/src/main/java/**/MainApplication.java:

```
import com.test.androidtoast.Package;

public class MainApplication extends Application implements ReactApplication {

    @Override
    protected List<ReactPackage> getPackages() {
        return Arrays.<ReactPackage>asList(
            new MainReactPackage(),
            new Package()     // android-toast
        );
    }
}
```


add this to your react-native js

```
import TestToast from 'android-toast'
TestToast.show('Hello TestToast', TestToast.LONG)

```

Ref: http://cmichel.io/how-to-create-react-native-android-library/ 

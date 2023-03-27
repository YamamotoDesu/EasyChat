# EasyChat

## [1 Project Setup | Chat application | Android Studio](https://www.youtube.com/watch?v=O4SQlpPZEdo)

<img width="300" alt="スクリーンショット 2023-03-27 11 34 44" src="https://user-images.githubusercontent.com/47273077/227826890-28974840-51f3-40ce-b57c-0783a866341f.png">

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/my_primary"
    tools:context=".SplashActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:gravity="center"
        android:orientation="vertical">

        <ImageView
            android:layout_width="160dp"
            android:layout_height="160dp"
            android:src="@drawable/chat_icon"
            app:tint="@color/my_secondary"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/app_name"
            android:textSize="40sp"
            android:textColor="@color/white"
            android:textStyle="bold"
            android:fontFamily="monospace"
            android:layout_marginTop="20dp"/>

        <ProgressBar
            android:layout_width="32dp"
            android:layout_height="wrap_content"/>

    </LinearLayout>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Developed by Kyo"
        android:layout_alignParentBottom="true"
        android:gravity="center"
        android:layout_marginBottom="20dp"
        android:textColor="@color/off_white"/>

</RelativeLayout>
```

themes.xml
```xml
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.EasyChat" parent="Theme.MaterialComponents.DayNight.NoActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/my_primary</item>
        <item name="colorPrimaryVariant">@color/my_primary</item>
        <item name="colorOnPrimary">@color/white</item>
```

AndroidMAnifest.xml
```xml
        <activity
            android:name=".SplashActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
            <meta-data
                android:name="android.app.lib_name"
                android:value="" />
        </activity>
        <activity
            android:name=".MainActivity"
            android:exported="false">

            <meta-data
                android:name="android.app.lib_name"
                android:value="" />
```

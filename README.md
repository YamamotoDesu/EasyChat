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

## [2 Phone Login Page Design | Chat application | Android Studio](https://www.youtube.com/watch?v=j7aBrr9Py-k)

<img width="300" alt="スクリーンショット 2023-03-30 9 42 59" src="https://user-images.githubusercontent.com/47273077/228699050-4259f8a6-b9c6-4803-9406-3a8fc354042e.png">

build.gradle
```
implementation 'com.hbb20:ccp:2.5.0'
```

btn_rounded_corner.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<shape android:shape="rectangle" xmlns:android="http://schemas.android.com/apk/res/android">

    <stroke android:width="1dp" android:color="@color/white"/>
    <corners android:radius="40dp" />
    <solid android:color="@color/white" />
</shape>
```

circular_bg.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<shape android:shape="oval" xmlns:android="http://schemas.android.com/apk/res/android">

</shape>
```

edit_text_rounded_center.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<shape android:shape="oval" xmlns:android="http://schemas.android.com/apk/res/android">

</shape>
```

SplashActivity.java
```java
public class SplashActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                startActivity(new Intent(SplashActivity.this, LoginPhoneNumberActivity.class));
                finish();
            }
        }, 3000);
    }
}
```

LoginPhoneNumberActivity.java
```java
public class LoginPhoneNumberActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_login_phone_number);
    }
}
```

activity_login_phone_number.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:layout_margin="20dp"
    android:weightSum="100"
    tools:context=".LoginPhoneNumberActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:layout_weight="20">
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/my_primary">
            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:textColor="@color/white"
                android:text="1" />
        </RelativeLayout>
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/light_gray">
            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:textColor="@color/white"
                android:text="2" />
        </RelativeLayout>
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/light_gray">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:text="3"
                android:textColor="@color/white" />
        </RelativeLayout>
    </LinearLayout>

    <ImageView
        android:layout_width="150dp"
        android:layout_height="150dp"
        android:src="@drawable/phone_icon"
        app:tint="@color/my_primary"
        android:layout_weight="10"/>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Enter mobile number"
        android:layout_gravity="center_vertical"
        android:letterSpacing="0.08"
        android:textStyle="bold"
        android:textSize="25dp"
        android:layout_weight="5"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center"
        android:layout_weight="5">

        <com.hbb20.CountryCodePicker
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            app:ccp_showFlag="false"
            app:ccp_showNameCode="false"/>

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="10dp"
            android:hint="Mobile"
            android:inputType="phone"
            android:layout_margin="10dp"
            android:background="@drawable/edit_text_rounded_center"
            android:elevation="5dp"
            />
    </LinearLayout>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="100dp"
        android:gravity="center_vertical"
        android:orientation="vertical"
        android:layout_weight="20">
        <Button
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:background="@drawable/btn_rounded_corner"
            android:text="Send otp"/>
        <ProgressBar
            android:layout_width="32dp"
            android:layout_height="wrap_content"
            android:indeterminateTint="@color/my_primary"
            android:layout_gravity="center"/>
    </LinearLayout>
</LinearLayout>
```

## [3 OTP & Username Page Design | Chat application | Android Studio](https://www.youtube.com/watch?v=iTORCXKExAg&list=WL&index=1)

<img width="300" alt="スクリーンショット 2023-03-31 21 52 58" src="https://user-images.githubusercontent.com/47273077/229125210-37fafa3f-d644-4706-b8c7-4a8e7e69b459.png">

activity_login_otp.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:layout_margin="20dp"
    android:weightSum="100"
    tools:context=".LoginUsernameActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:layout_weight="20">
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/light_gray">
            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:textColor="@color/white"
                android:text="1" />
        </RelativeLayout>
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/light_gray">
            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:textColor="@color/white"
                android:text="2" />
        </RelativeLayout>
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/my_primary">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:text="3"
                android:textColor="@color/white" />
        </RelativeLayout>
    </LinearLayout>

    <ImageView
        android:layout_width="150dp"
        android:layout_height="150dp"
        android:src="@drawable/person_icon"
        app:tint="@color/my_primary"
        android:layout_weight="10"/>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Enter your username"
        android:layout_gravity="center_vertical"
        android:letterSpacing="0.08"
        android:textStyle="bold"
        android:textSize="25dp"
        android:layout_weight="5"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center"
        android:layout_weight="5">

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="10dp"
            android:hint="Username"
            android:inputType="phone"
            android:layout_margin="10dp"
            android:background="@drawable/edit_text_rounded_center"
            android:elevation="5dp"
            android:id="@+id/login_username"
            />
    </LinearLayout>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="100dp"
        android:gravity="center_vertical"
        android:orientation="vertical"
        android:layout_weight="20">
        <Button
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:background="@drawable/btn_rounded_corner"
            android:text="Let me in"
            android:id="@+id/login_let_me_in_btn"/>
        <ProgressBar
            android:layout_width="32dp"
            android:layout_height="wrap_content"
            android:indeterminateTint="@color/my_primary"
            android:layout_gravity="center"
            android:id="@+id/login_progress_bar"/>
    </LinearLayout>
</LinearLayout>
```

<img width="300" alt="スクリーンショット 2023-03-31 21 51 58" src="https://user-images.githubusercontent.com/47273077/229124945-b570a01c-ee64-4931-8ba4-c86832c64209.png">

activity_login_username.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:layout_margin="20dp"
    android:weightSum="100"
    tools:context=".LoginUsernameActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:layout_weight="20">
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/light_gray">
            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:textColor="@color/white"
                android:text="1" />
        </RelativeLayout>
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/light_gray">
            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:textColor="@color/white"
                android:text="2" />
        </RelativeLayout>
        <RelativeLayout
            android:layout_width="32dp"
            android:layout_height="32dp"
            android:layout_margin="10dp"
            android:background="@drawable/circular_bg"
            android:backgroundTint="@color/my_primary">

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerInParent="true"
                android:text="3"
                android:textColor="@color/white" />
        </RelativeLayout>
    </LinearLayout>

    <ImageView
        android:layout_width="150dp"
        android:layout_height="150dp"
        android:src="@drawable/person_icon"
        app:tint="@color/my_primary"
        android:layout_weight="10"/>

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Enter your username"
        android:layout_gravity="center_vertical"
        android:letterSpacing="0.08"
        android:textStyle="bold"
        android:textSize="25dp"
        android:layout_weight="5"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:gravity="center"
        android:layout_weight="5">

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="10dp"
            android:hint="Username"
            android:inputType="phone"
            android:layout_margin="10dp"
            android:background="@drawable/edit_text_rounded_center"
            android:elevation="5dp"
            android:id="@+id/login_username"
            />
    </LinearLayout>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="100dp"
        android:gravity="center_vertical"
        android:orientation="vertical"
        android:layout_weight="20">
        <Button
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:background="@drawable/btn_rounded_corner"
            android:text="Let me in"
            android:id="@+id/login_let_me_in_btn"/>
        <ProgressBar
            android:layout_width="32dp"
            android:layout_height="wrap_content"
            android:indeterminateTint="@color/my_primary"
            android:layout_gravity="center"
            android:id="@+id/login_progress_bar"/>
    </LinearLayout>
</LinearLayout>
```

## [4 Login with Phone number | Chat application | Android Studio](https://www.youtube.com/watch?v=ZRTXylK-tzE)

<img width="300" alt="スクリーンショット 2023-03-31 21 51 58" src="https://github.com/YamamotoDesu/EasyChat/blob/main/easychat.gif">


LoginPhoneNumberActivity.kt
```kt
public class LoginPhoneNumberActivity extends AppCompatActivity {

    CountryCodePicker countryCodePicker;
    EditText phoneInput;
    Button sendOtpBtn;
    ProgressBar progressBar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_login_phone_number);

        countryCodePicker = findViewById(R.id.login_countrycode);
        phoneInput = findViewById(R.id.login_mobile_number);
        sendOtpBtn = findViewById(R.id.send_otp_btn);
        progressBar = findViewById(R.id.login_progress_bar);

        progressBar.setVisibility(View.GONE);


        countryCodePicker.registerCarrierNumberEditText(phoneInput);
        sendOtpBtn.setOnClickListener((v) -> {
            if (!countryCodePicker.isValidFullNumber()) {
                phoneInput.setError("Phone number not valid");
                return;
            }
            Intent intent = new Intent(LoginPhoneNumberActivity.this, LoginOtpActivity.class);
            intent.putExtra("phone", countryCodePicker.getFullNumberWithPlus());
            startActivity(intent);
        });
    }
```


LoginOtpActivity.kt
```kt
public class LoginOtpActivity extends AppCompatActivity {

    String phoneNumber;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_login_username);

        phoneNumber = getIntent().getExtras().getString("phone");
        Toast.makeText(getApplicationContext(), phoneNumber, Toast.LENGTH_LONG).show();

    }
}
```


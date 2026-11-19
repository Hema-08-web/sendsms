
# Ex.No:3 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
Program to create and design an android application Send SMS using Intent.
Developed by: HEMA D
Registeration Number : 212225220038
```
## ActivityMain.xml
```
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp"
    android:gravity="center">

    <EditText
        android:id="@+id/etNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Mobile Number"
        android:inputType="phone"/>

    <EditText
        android:id="@+id/etMessage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Message"
        android:layout_marginTop="20dp"
        android:minLines="4"
        android:gravity="top"/>

    <Button
        android:id="@+id/btnSend"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Send SMS"
        android:layout_marginTop="30dp"/>

</LinearLayout>
```

## Activitymain.java
```
package com.example.smsintent;


import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    EditText etNumber, etMessage;
    Button btnSend;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        etNumber = findViewById(R.id.etNumber);
        etMessage = findViewById(R.id.etMessage);
        btnSend = findViewById(R.id.btnSend);

        btnSend.setOnClickListener(v -> {

            String number = etNumber.getText().toString();
            String message = etMessage.getText().toString();

            Intent intent = new Intent(Intent.ACTION_SENDTO);

            intent.setData(Uri.parse("smsto:" + number));

            intent.putExtra("sms_body", message);

            startActivity(intent);

        });

    }
}
```

## OUTPUT

<img width="1919" height="1022" alt="Screenshot 2026-08-03 133845" src="https://github.com/user-attachments/assets/bd400bbd-26e3-4040-bcfa-875c034fe72d" />
<img width="1919" height="1024" alt="Screenshot 2026-08-03 133902" src="https://github.com/user-attachments/assets/8b32df36-d956-4dcc-bf9c-a65b95a4cab8" />
<img width="1919" height="1020" alt="Screenshot 2026-08-03 133918" src="https://github.com/user-attachments/assets/5555786b-890d-451b-a4fa-4fdddf0bf9f2" />

## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.

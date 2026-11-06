# Ex.No:2(A) Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio<hr>

## ALGORITHM 
STEP 1: Create a new project in Android Studio.

STEP 2: Design the user interface using XML with an EditText field and an Implicit Intent button.

STEP 3: Initialize the EditText and Button components in the MainActivity Java file.

STEP 4: Set an OnClickListener for the Implicit Intent button.

STEP 5: Get the website URL from the EditText field.

STEP 6: Create an Intent using Intent.ACTION_VIEW.

STEP 7: Set the website URL using Uri.parse().

STEP 8: Call startActivity() to open the Gmail website in the browser.

STEP 9: Run the application and verify the output.

RESULT: The Gmail website is successfully opened using Implicit Intent.


## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by:Iyyappan S
Registeration Number :  212225230108
*/
```
MainActivity.java
```
package com.example.implicintindent;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {

    EditText url;
    Button btnImplicit;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        url = findViewById(R.id.url);
        btnImplicit = findViewById(R.id.btnImplicit);
        btnImplicit.setOnClickListener(v -> {
            String website = url.getText().toString();
            Intent intent = new Intent(Intent.ACTION_VIEW);
            intent.setData(Uri.parse(website));
            startActivity(intent);
        });
    }
}
```

Activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="IMPLICIT INTENT"
        android:textSize="25sp"
        android:textStyle="bold"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="150dp"/>

    <EditText
        android:id="@+id/url"
        android:layout_width="300dp"
        android:layout_height="wrap_content"
        android:hint="Enter Website"
        android:text="https://www.gmail.com"
        android:inputType="textUri"
        app:layout_constraintTop_toBottomOf="@id/textView"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="40dp"/>

    <Button
        android:id="@+id/btnImplicit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Implicit Intent"
        app:layout_constraintTop_toBottomOf="@id/url"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="30dp"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```
## OUTPUT

<img width="1722" height="913" alt="image" src="https://github.com/user-attachments/assets/ef68650f-447c-4edf-961b-f389af858925" />



## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.

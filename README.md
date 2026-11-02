# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1. Start the Android Studio application.

2. Create a new project using Empty Views Activity.

3. Design the user interface using an EditText and a Button named Navigate.

4. Initialise the EditText and Button components in the Java activity.

5. Get the website URL entered by the user from the EditText.

6. Check whether the entered URL is empty.

7. Create an Implicit Intent using Intent.ACTION_VIEW.

8. Convert the website URL into a URI using Uri.parse().

9. Use startActivity() to launch the browser.

10. Run the application and verify that the Gmail webpage opens successfully.

11. Stop the application.

## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: NAVEEN KUMAR E
Registeration Number : 212224230181
*/
```
Main Activity.java
```java
package com.example.implicitintent;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText urlText;
    Button navigateButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        urlText = findViewById(R.id.urlText);
        navigateButton = findViewById(R.id.navigateButton);

        navigateButton.setOnClickListener(v -> {

            String url = urlText.getText().toString().trim();

            if (url.isEmpty()) {
                Toast.makeText(this,
                        "Enter a website URL",
                        Toast.LENGTH_SHORT).show();
                return;
            }

            if (!url.startsWith("http://") &&
                    !url.startsWith("https://")) {
                url = "https://" + url;
            }

            Intent intent = new Intent(
                    Intent.ACTION_VIEW,
                    Uri.parse(url)
            );

            startActivity(intent);
        });
    }
}

```

Activity_main.xml
```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <EditText
        android:id="@+id/urlText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter website URL"
        android:inputType="textUri"
        android:text="www.gmail.com" />

    <Button
        android:id="@+id/navigateButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Navigate" />

</LinearLayout>

```

## OUTPUT

<img width="1920" height="1160" alt="image" src="https://github.com/user-attachments/assets/fbbaebb0-05df-4558-8f54-c4ca2d8fdf83" />


<img width="1920" height="1160" alt="image" src="https://github.com/user-attachments/assets/b03f502a-3f6e-4d58-8f29-f321daa5dbc4" />





## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.



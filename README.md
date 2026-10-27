Experiment 01: Activity Life Cycle

Aim

To create an Android application to understand the life cycle of an Activity.

Objective

To develop an Android application and understand the Activity life cycle in different scenarios.

Apparatus / Tools / Equipment

- Android Studio
- Android Emulator or Android Device
- Java
- XML

Theory

The Activity Life Cycle describes the different states an Android Activity goes through from creation to destruction.

The main life cycle methods are:

- "onCreate()" – Called when the Activity is first created.
- "onStart()" – Called when the Activity becomes visible.
- "onResume()" – Called when the Activity enters the foreground and the user can interact with it.
- "onPause()" – Called when the Activity loses focus.
- "onStop()" – Called when the Activity is no longer visible.
- "onRestart()" – Called when a stopped Activity is about to start again.
- "onDestroy()" – Called before the Activity is destroyed.

Procedure

1. Open Android Studio and create a new Android project.
2. Create a "MainActivity" and implement the Activity life cycle methods.
3. Add Log messages inside each life cycle method.
4. Create the user interface using "activity_main.xml".
5. Run the application on an Android Emulator or Android device.
6. Open Logcat using View → Tool Windows → Logcat.
7. Observe the life cycle methods when the Activity starts, pauses, stops, restarts, and resumes.
8. Record the output displayed in Logcat.

Program

1. MainActivity.java

package com.example.activitylifecycle;

import android.os.Bundle;
import android.util.Log;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    String tag = "Activity Life Cycle";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Log.d(tag, "In the onCreate() event");
    }

    @Override
    protected void onStart() {
        super.onStart();
        Log.d(tag, "In the onStart() event");
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        Log.d(tag, "In the onRestart() event");
    }

    @Override
    protected void onResume() {
        super.onResume();
        Log.d(tag, "In the onResume() event");
    }

    @Override
    protected void onPause() {
        super.onPause();
        Log.d(tag, "In the onPause() event");
    }

    @Override
    protected void onStop() {
        super.onStop();
        Log.d(tag, "In the onStop() event");
    }

    @Override
    protected void onDestroy() {
        super.onDestroy();
        Log.d(tag, "In the onDestroy() event");
    }
}

2. activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome to MAD LAB"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>

Sample Output

When the application is launched, the following messages appear in Logcat:

In the onCreate() event
In the onStart() event
In the onResume() event

When the Activity is interrupted and becomes invisible:

In the onPause() event
In the onStop() event

When the stopped Activity is opened again:

In the onRestart() event
In the onStart() event
In the onResume() event

When the Activity is finished and destroyed:

In the onPause() event
In the onStop() event
In the onDestroy() event

Note: The exact callback sequence depends on how the Activity is interrupted or closed. Android may not call "onDestroy()" if the process is terminated unexpectedly.

Result

Thus, an Android application was successfully created to understand and demonstrate the Activity Life Cycle using Java, XML, and Logcat.

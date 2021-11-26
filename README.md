# Второе окно

MainActivity.java:

      package com.example.second_activity;

      import androidx.appcompat.app.AppCompatActivity;

      import android.annotation.SuppressLint;
      import android.content.Intent;
      import android.os.Bundle;
      import android.util.Log;
      import android.view.View;

      public class MainActivity extends AppCompatActivity implements View.OnClickListener {
          final String TAG = "States";

          @Override
          protected void onCreate(Bundle savedInstanceState) {
              super.onCreate(savedInstanceState);
              setContentView(R.layout.activity_main);
              Log.d(TAG, "MainActivity: onCreate()");
              findViewById(R.id.btnActTwo).setOnClickListener(this);
          }

          @SuppressLint("NonConstantResourceId")
          @Override
          public void onClick(View v) {
              switch (v.getId()) {
                  case R.id.btnActTwo:
                      Intent intent = new Intent(this, MainActivity2.class);
                      startActivity(intent);
                      break;
                  default:
                      break;
              }
          }

          @Override
          protected void onStart() {
              super.onStart();
              Log.d(TAG, "MainActivity: onStart()");
          }

          @Override
          protected void onResume() {
              super.onResume();
              Log.d(TAG, "MainActivity: onResume()");
          }

          @Override
          protected void onPause() {
              super.onPause();
              Log.d(TAG, "MainActivity: onPause()");
          }

          @Override
          protected void onStop() {
              super.onStop();
              Log.d(TAG, "MainActivity: onStop()");
          }

          @Override
          protected void onDestroy() {
              super.onDestroy();
              Log.d(TAG, "MainActivity: onDestroy()");
          }

          @Override
          protected void onRestart() {
              super.onRestart();
              Log.d(TAG, "MainActivity: onRestart()");
          }

      }
      
MainActivity2.java:

      package com.example.second_activity;

      import androidx.appcompat.app.AppCompatActivity;

      import android.os.Bundle;

      public class MainActivity2 extends AppCompatActivity {

          @Override
          protected void onCreate(Bundle savedInstanceState) {
              super.onCreate(savedInstanceState);
              setContentView(R.layout.activity_main2);
          }
      }
      
activity_main.xml:

      <?xml version="1.0" encoding="utf-8"?>
      <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
          android:layout_width="fill_parent"
          android:layout_height="fill_parent"
          android:orientation="vertical">

          <Button
              android:id="@+id/btnActTwo"
              android:layout_width="wrap_content"
              android:layout_height="wrap_content"
              android:text="@string/go_to_activity_two" />
      </LinearLayout>
     
activity_main2.xml:

      <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
          android:layout_width="match_parent"
          android:layout_height="match_parent"
          android:orientation="vertical">

          <TextView
              android:id="@+id/textView1"
              android:layout_width="wrap_content"
              android:layout_height="wrap_content"
              android:text="@string/this_is_activity_two" />
      </LinearLayout>
      
strings.xml:

      <resources>
          <string name="app_name">second_activity</string>
          <string name="go_to_activity_two">Go to Activity Two</string>
          <string name="this_is_activity_two">This is Activity Two</string>
      </resources>
      
Результат работы программы:




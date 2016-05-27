# Android-stuff

//trying my hand at some basic android api.


package com.example.huang.mybasiccalculator;

        import android.support.v7.app.AppCompatActivity;
        import android.os.Bundle;
        import android.view.View;
        import android.widget.Button;
        import android.widget.EditText;
        import android.widget.TextView;


public class MainActivity extends AppCompatActivity implements View.OnClickListener {
    private Button btnAdd,btnsub,btndivide,btnmul;
    private TextView tvresult;
    private EditText etfirst,etsecond;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(android.R.layout.activity_list_item);
        init();
    }
    private void init(){
        btnAdd = (Button)findViewById(R.id.btnAdd);
        btnsub = (Button)findViewById(R.id.btnSubtract);
        btndivide = (Button)findViewById(R.id.btnDivision);
        btnmul = (Button)findViewById(R.id.btnMultiplication);
        etfirst = (EditText)findViewById(R.id.etFirstNumber);
        etsecond = (EditText)findViewById(R.id.etSecondNumber);
        tvresult= (TextView)findViewById(R.id.tvResult);

        btnAdd.setOnClickListener(this);
        btnsub.setOnClickListener(this);
        btndivide.setOnClickListener(this);
        btnmul.setOnClickListener(this);
    }

    @Override
    public void onClick(View view) {
        String num1 = etfirst.getText().toString();
        String num2 = etsecond.getText().toString();

        switch (view.getId()){

            case R.id.btnAdd:

            int addition = Integer.parseInt(num1) + Integer.parseInt(num2);
            tvresult.setText(String.valueOf(addition));
                break;
            case R.id.btnSubtract:

            int subtraction = Integer.parseInt(num1) - Integer.parseInt(num2);
            tvresult.setText(String.valueOf(subtraction));break;
            case R.id.btnDivision:
                try{int division = Integer.parseInt(num1) / Integer.parseInt(num2);
                    tvresult.setText(String.valueOf(division));
                }catch(Exception e){
                    tvresult.setText("Cannot DIVIDE");
                }

                break;

            case R.id.btnMultiplication:
                ;
            int multiply = Integer.parseInt(num1) * Integer.parseInt(num2);
            tvresult.setText(String.valueOf(multiply));break;
        }

    }
}

//activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="com.example.huang.mybasiccalculator.MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="My Basic Calculator"
        android:id="@+id/textView"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:textColor="#008888" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:text="First Number"
        android:id="@+id/textView2"
        android:layout_below="@+id/textView"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true" />

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:inputType="number"
        android:ems="10"
        android:id="@+id/etFirstNumber"
        android:layout_below="@+id/textView2"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:text="Second Number"
        android:id="@+id/textView3"
        android:layout_below="@+id/etFirstNumber"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true" />

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:inputType="number"
        android:ems="10"
        android:id="@+id/etSecondNumber"
        android:layout_below="@+id/textView3"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true" />

    <LinearLayout
        android:orientation="horizontal"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_below="@+id/etSecondNumber"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="+"
            android:id="@+id/btnAdd" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="-"
            android:id="@+id/btnSubtract" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="/"
            android:id="@+id/btnDivision" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="*"
            android:id="@+id/btnMultiplication" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textAppearance="?android:attr/textAppearanceLarge"
            android:id="@+id/tvResult"
            android:textColor="#00ffff" />
    </LinearLayout>

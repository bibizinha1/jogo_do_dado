# jogo_do_dado
projeto_ceprocamp_jogo
//MainActivity.java
package com.example.jogo_do_dado;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;

import java.util.Random;

public class MainActivity extends AppCompatActivity {
    private ImageView dado;

    private Button button;
    private int[] numerosDoDado = {
            R.drawable.diceum,
            R.drawable.dicedois,
            R.drawable.dicetres,
            R.drawable.quatro_dado,
            R.drawable.cinco_dado,
            R.drawable.diceseis,


    };


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        dado=findViewById(R.id.dado);
        button=findViewById(R.id.button);
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                int numerosAleatorios = new Random().nextInt(numerosDoDado.length);
                dado.setImageResource(numerosDoDado[numerosAleatorios]);

            }
        });

        }
    }

//activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/black"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/dado"
        android:layout_width="235dp"
        android:layout_height="226dp"
        android:layout_centerInParent="true"
        android:src="@drawable/diceum" />

    <Button
        android:id="@+id/button"
        android:layout_width="281dp"
        android:layout_height="128dp"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:layout_marginBottom="57dp"
        android:text="Gire o dado" />


</RelativeLayout>

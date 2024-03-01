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

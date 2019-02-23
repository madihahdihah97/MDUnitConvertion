# MDUnitConvertion
package com.example.mdunitconvertion;


import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import java.text.DecimalFormat;

public class MainActivity extends AppCompatActivity {
     EditText meters,inches,feet,yards,miles, nautical miles;
     Button resetButton, calculateButton;

     private static DecimalFormat decimalFormat = new DecimalFormat ('.##');

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        meters = findViewById(R.id.meters);
        inches = findViewById(R.id.inches);
        feet = findViewById(R.id.feet);
        yards = findViewById(R.id.yards);
        miles = findViewById(R.id.miles);
        nauticalMiles = findViewById(R.id.nauticalMiles);

        resetButton = findViewById(R.id.resetButton);
        calculateButton = findViewById(R.id.calculateButton);

        calculateButton.setOnClickListener(new View.OnClickListener() {
            @Override


            public void onClick(View v) {
                final String meters = meters.getText().toString();
                final String inches = inches.getText().toString();
                final String feet = feet.getText().toString();
                final String yards = yards.getText().toString();
                final String miles = miles.getText().toString();
                final String nauticalMiles = nauticalMiles.getText().toString();

                double valueMeters, valueInches, valueFeet, valueYards, valueMiles;

                /* Calculate meters */
                if (inches.equal("") && meters.equals(""))
                    valueInches = Double.parseDouble(inches);
                valueMeters = valueInches * 40.265;
                valueFeet = valueInches * 3.452;
                valueYards = valueInches * 2.332;
                valueMiles = valueInches * 1.456;
                valueNauticalMiles = valueInches * 2.456;

                String callValueInches = decimalFormat.format(valueInches);
                String callValueMeters = decimalFormat.format(valueMeters);
                String callValueFeets = decimalFormat.format(valueFeets);
                String callValueYards = decimalFormat.format(valueYards);
                String callValueNauticalMiles = decimalFormat.format(valueNauticalMiles);

                meters.setText(callValueMeters);
                inches.setText(callValueInches);
                feet.setText(callValueFeet);
                yards.setText(callValueYards);
                miles.setText(callValueMiles);
                nauticalMiles.setText(nauticalMiles);
            }

            valueMeters =Double.parseDouble(meters);
            valueMeters =valueMeters /40.265;
            valueMeters =valueMeters *3.452;

            String callValueMeters = decimalFormat.format(valueMeters);
            String callValueInches = decimalFormat.format(valueInches);

                    meters.setText(callValueMeters);
                    inches.setText(callValueInches);
        }
                clearButton.setOnClickListener(new View.OnClickListener()
                {
                    @Override
                    public void onClick(View v)
                    {
                        meters.setText("");
                        inches.setText("");
                        feet.setText("");
                        yards.setText("");
                        miles.setText("");
                        nauticalMiles.setText("");


            }
        }


    }
}



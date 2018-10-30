# ProyectoMovil1ConvertidorgradosCF
package convertidorgf.jhalmarpiloso.facci.convertidorgf;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class ActividadPrincipal extends AppCompatActivity implements View.OnClickListener {
    EditText centigrados, fahrenheit;
    Button ConvertidorCentigrados, ConvertirFahrenheit;
    TextView DatosCentigrados, DatosFahrenheit;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_actividad_principal);
        Log.e("Hola mundo", "Jhalmar Michael Piloso Loor")
        centigrados = (EditText) findViewById(R.id.TXTCenti);
        fahrenheit = (EditText) findViewById(R.id.TXTFahren);
        ConvertidorCentigrados = (Button) findViewById(R.id.BTNCenti);
        ConvertirFahrenheit = (Button) findViewById(R.id.BTNFahren);
        DatosCentigrados = (TextView) findViewById(R.id.LBLCenti);
        DatosFahrenheit = (TextView) findViewById(R.id.LBLFahren);

        ConvertidorCentigrados.setOnClickListener((View.OnClickListener) This);
        ConvertirFahrenheit.setOnClickListener((View.OnClickListener) This);
    }
    public void onClick(View v) {
    switch (v.getId()) {
        case R.id.BTNCenti:
            if (centigrados.getText().toString().isEmpty()) {
                Toast.makeText(ActividadPrincipal.this, "Ingrese un Valor", Toast.LENGTH_LONG).show();
            } else {
                Double Centigra = Double.valueOf(centigrados.getText().toString());
                Double Fahrenhe = (Centigra * 1.8) + 32;
                Toast.makeText(ActividadPrincipal.this, String.valueOf(Fahrenhe) + "ºF", Toast.LENGTH_LONG).show();
                DatosFahrenheit.setText(String.valueOf(Fahrenhe) + "ºF");
                centigrados.setText("");
            }
            break;

        case R.id.BTNFahren:
            if (fahrenheit.getText().toString().isEmpty()) {
                Toast.makeText(ActividadPrincipal.this, "Ingrese un Valor", Toast.LENGTH_LONG).show();
            } else {
                Double Fahrenhei = Double.valueOf(fahrenheit.getText().toString());
                Double Centigrad = (Fahrenhei - 32) / 1.8;
                Toast.makeText(ActividadPrincipal.this, String.valueOf(Centigrad) + "ºC", Toast.LENGTH_LONG).show();
                DatosFahrenheit.setText(String.valueOf(Centigrad) + "ºC");
                centigrados.setText("");
            }
            break;
    }
}

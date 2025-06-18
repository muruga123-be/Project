# Activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:orientation="vertical"
android:padding="16dp"
android:background="#444444"
android:gravity="center_horizontal">
<!-- Display/Edit Text for showing current input -->
<TextView
android:id="@+id/tv_title"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Calculator"
android:textSize="50sp"
android:textColor="#FFFFFF"
android:layout_marginTop="50dp"
android:textStyle="bold"
android:layout_marginBottom="40dp" />
<EditText
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:id="@+id/tv"
android:textSize="42sp"
android:inputType="none"
android:layout_marginTop="60dp"
android:layout_marginBottom="190dp"
android:gravity="end"
android:textColor="#000000"
android:background="#f0f0f0"/>
<!-- First row of buttons -->
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:layout_marginBottom="20dp"
android:weightSum="4">
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b9"
android:layout_weight="1"
android:text="9"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b8"
android:layout_weight="1"
android:text="8"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b7"
android:layout_weight="1"
android:text="7"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/bpl"
android:layout_weight="1"
android:text="+"
android:textColor="#ffffff"
android:textSize="24sp" />
</LinearLayout>
<!-- Second row of buttons -->
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:layout_marginBottom="20dp"
android:weightSum="4">
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b6"
android:layout_weight="1"
android:text="6"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b5"
android:layout_weight="1"
android:text="5"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b4"
android:layout_weight="1"
android:text="4"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/bmin"
android:layout_weight="1"
android:text="-"
android:textColor="#ffffff"
android:textSize="24sp" />
</LinearLayout>
<!-- Third row of buttons -->
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:layout_marginBottom="20dp"
android:weightSum="4">
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b3"
android:layout_weight="1"
android:text="3"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b2"
android:layout_weight="1"
android:text="2"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b1"
android:layout_weight="1"
android:text="1"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/bmul"
android:layout_weight="1"
android:text="*"
android:textColor="#ffffff"
android:textSize="24sp" />
</LinearLayout>
<!-- Fourth row of buttons -->
<LinearLayout
android:layout_width="match_parent"
android:layout_height="wrap_content"
android:orientation="horizontal"
android:layout_marginBottom="20dp"
android:weightSum="5">
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/bd"
android:layout_weight="1"
android:text="."
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/b0"
android:layout_weight="1"
android:text="0"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/bcl"
android:layout_weight="1"
android:text="Cl"
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/beq"
android:layout_weight="1"
android:text="="
android:textColor="#ffffff"
android:textSize="24sp" />
<Button
android:layout_width="0dp"
android:layout_height="wrap_content"
android:id="@+id/bdiv"
android:layout_weight="1"
android:text="/"
android:textColor="#ffffff"
android:textSize="24sp" />
</LinearLayout>
</LinearLayout>
Main_Activity.java
package com.example.calculator;
import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
public class MainActivity extends Activity implements View.OnClickListener {
Button nine, eig, sev, six, fiv, four, thr, two, one, zero, dot, plus, mins, div, mul, eq, cl;
EditText et;
String currentInput = "0"; // Current input string for numbers
int result = 0; // Store the result of the calculation
char lastOperator = ' '; // Store the last operator used
@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);
nine = findViewById(R.id.b9);
eig = findViewById(R.id.b8);
sev = findViewById(R.id.b7);
six = findViewById(R.id.b6);
fiv = findViewById(R.id.b5);
four = findViewById(R.id.b4);
thr = findViewById(R.id.b3);
two = findViewById(R.id.b2);
one = findViewById(R.id.b1);
zero = findViewById(R.id.b0);
dot = findViewById(R.id.bd);
plus = findViewById(R.id.bpl);
mins = findViewById(R.id.bmin);
div = findViewById(R.id.bdiv);
mul = findViewById(R.id.bmul);
eq = findViewById(R.id.beq);
cl = findViewById(R.id.bcl);
et = findViewById(R.id.tv);
// Set OnClickListener for Buttons
nine.setOnClickListener(this);
eig.setOnClickListener(this);
sev.setOnClickListener(this);
six.setOnClickListener(this);
fiv.setOnClickListener(this);
four.setOnClickListener(this);
thr.setOnClickListener(this);
two.setOnClickListener(this);
one.setOnClickListener(this);
zero.setOnClickListener(this);
dot.setOnClickListener(this);
plus.setOnClickListener(this);
mins.setOnClickListener(this);
div.setOnClickListener(this);
mul.setOnClickListener(this);
eq.setOnClickListener(this);
cl.setOnClickListener(this);
}
@Override
public void onClick(View v) {
int id = v.getId();
if (id == R.id.b0 || id == R.id.b1 || id == R.id.b2 || id == R.id.b3 ||
id == R.id.b4 || id == R.id.b5 || id == R.id.b6 || id == R.id.b7 ||
id == R.id.b8 || id == R.id.b9) {
String inputDigit = ((Button) v).getText().toString();
if (currentInput.equals("0")) {
currentInput = inputDigit; // Start with the clicked number
} else {
currentInput += inputDigit; // Append further digits
}
et.setText(currentInput); // Update the display
if (lastOperator == '=') {
result = 0; // Reset result if "=" was pressed
lastOperator = ' '; // Reset operator
}
} else if (id == R.id.bpl) {
compute(); // Perform calculation for addition
lastOperator = '+'; // Update last operator
} else if (id == R.id.bmin) {
compute(); // Perform calculation for subtraction
lastOperator = '-'; // Update last operator
} else if (id == R.id.bdiv) {
compute(); // Perform calculation for division
lastOperator = '/'; // Update last operator
} else if (id == R.id.bmul) {
compute(); // Perform calculation for multiplication
lastOperator = '*'; // Update last operator
} else if (id == R.id.beq) {
compute(); // Perform final calculation
lastOperator = '='; // Update last operator
} else if (id == R.id.bcl) {
result = 0; // Reset result to zero
currentInput = "0"; // Reset input
lastOperator = ' '; // Reset operator
et.setText("0"); // Clear the display
}
}
private void compute() {
int inputNumber = Integer.parseInt(currentInput); // Convert current input to integer
currentInput = "0"; // Reset current input after processing
switch (lastOperator) {
case ' ':
result = inputNumber; // If no operator, set result to current input
break;
case '+':
result += inputNumber; // Perform addition
break;
case '-':
result -= inputNumber; // Perform subtraction
break;
case '*':
result *= inputNumber; // Perform multiplication
break;
case '/':
if (inputNumber != 0) {
result /= inputNumber; // Perform division, check for divide by zero
} else {
et.setText("Error"); // Display error if division by zero
return;
}
break;
case '=':
break; // Do nothing on '=' as result is already computed
}
et.setText(String.valueOf(result)); // Update the display with the result
}
}

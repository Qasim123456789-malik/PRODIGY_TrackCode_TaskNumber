# PRODIGY_TrackCode_TaskNumber
Task-01  Build a calculator app that can perform basic arithmetic operations.
Code:
import React, { useState } from 'react';
import { View, Text, TouchableOpacity, StyleSheet } from 'react-native';

export default function App() {
  const [input, setInput] = useState('');
  const [output, setOutput] = useState('');

  // Handle button press
  const handleButtonPress = (value) => {
    setInput(input + value);
  };

  // Handle clear button
  const handleClear = () => {
    setInput('');
    setOutput('');
  };

  // Handle evaluation of the input
  const handleEqual = () => {
    try {
      setOutput(eval(input).toString());
    } catch (error) {
      setOutput('Error');
    }
  };

  // Handle backspace button
  const handleBackspace = () => {
    setInput(input.slice(0, -1));
  };

  return (
    <View style={styles.container}>
      <View style={styles.result}>
        <Text style={styles.input}>{input}</Text>
        <Text style={styles.output}>{output}</Text>
      </View>

      <View style={styles.buttons}>
        <View style={styles.row}>
          <Button label="1" onPress={() => handleButtonPress('1')} />
          <Button label="2" onPress={() => handleButtonPress('2')} />
          <Button label="3" onPress={() => handleButtonPress('3')} />
          <Button label="+" onPress={() => handleButtonPress('+')} />
        </View>
        <View style={styles.row}>
          <Button label="4" onPress={() => handleButtonPress('4')} />
          <Button label="5" onPress={() => handleButtonPress('5')} />
          <Button label="6" onPress={() => handleButtonPress('6')} />
          <Button label="-" onPress={() => handleButtonPress('-')} />
        </View>
        <View style={styles.row}>
          <Button label="7" onPress={() => handleButtonPress('7')} />
          <Button label="8" onPress={() => handleButtonPress('8')} />
          <Button label="9" onPress={() => handleButtonPress('9')} />
          <Button label="*" onPress={() => handleButtonPress('*')} />
        </View>
        <View style={styles.row}>
          <Button label="C" onPress={handleClear} />
          <Button label="0" onPress={() => handleButtonPress('0')} />
          <Button label="=" onPress={handleEqual} />
          <Button label="/" onPress={() => handleButtonPress('/')} />
        </View>
        <View style={styles.row}>
          <Button label="⌫" onPress={handleBackspace} />
        </View>
      </View>
    </View>
  );
}

// Button component for calculator buttons
const Button = ({ label, onPress }) => (
  <TouchableOpacity style={styles.button} onPress={onPress}>
    <Text style={styles.buttonText}>{label}</Text>
  </TouchableOpacity>
);

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f0f0f0',
  },
  result: {
    width: '90%',
    padding: 20,
    backgroundColor: '#fff',
    marginBottom: 30,
    borderRadius: 10,
    elevation: 3,
  },
  input: {
    fontSize: 30,
    textAlign: 'right',
    color: '#333',
  },
  output: {
    fontSize: 40,
    textAlign: 'right',
    color: '#000',
  },
  buttons: {
    width: '90%',
  },
  row: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    marginBottom: 20,
  },
  button: {
    width: '20%',
    height: 70,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#4CAF50',
    borderRadius: 10,
  },
  buttonText: {
    fontSize: 30,
    color: 'white',
  },
});


![image](https://github.com/user-attachments/assets/f6173636-1525-4685-bee4-ba56cd1e4ea4)

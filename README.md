# Currency-coverter
Covert Your Currency into any Country of Currency

# Real Time Currency Converter

This repository contains a Python-based project for a **Real-Time Currency Converter** that provides dynamic functionality for currency conversion. The application uses real-time exchange rates to convert between multiple currencies, making it highly useful for business, finance, and daily money exchange purposes.

## Table of Contents
1. [Abstract](#abstract)
2. [Introduction](#introduction)
    - [Background of the Study](#background-of-the-study)
    - [Problem Statement](#problem-statement)
    - [Objectives of the Study](#objectives-of-the-study)
3. [Related Concepts](#related-concepts)
    - [What is Exchange Rate?](#what-is-exchange-rate)
    - [Exchange Rate Example](#exchange-rate-example)
4. [Requirements](#requirements)
    - [Hardware Requirements](#hardware-requirements)
    - [Software Requirements](#software-requirements)
5. [Implementation](#implementation)
    - [Steps to Build the Python Project](#steps-to-build-the-python-project)
6. [Conclusion](#conclusion)
7. [References](#references)

---

## Abstract

Different countries use different currencies, and exchange rates between these currencies vary daily. The **Currency Converter** project is a Python-based application that provides real-time currency conversion. Users can choose the source and target currencies, input the amount, and get the converted value. This project is especially useful for businesses and financial operations that involve regular money transfers and conversions.

---

## Introduction

### Background of the Study
Currency conversion can be a complex process, especially for individuals working in currency exchange offices. This project addresses the challenges faced in recognizing and converting currencies by implementing an automated system that utilizes image processing and pattern recognition techniques. 

### Problem Statement
Manual currency recognition and conversion can be error-prone and time-consuming. This project aims to automate the process, reducing human intervention and improving accuracy.

### Objectives of the Study
1. Develop a system capable of converting between five major currencies: INR, AUD, EUR, NGN, and USD.
2. Implement a mechanism to store and utilize exchange rates for conversion.
3. Integrate neural network-based methods for currency recognition.
4. Use digital image processing to extract data from currency images.

---

## Related Concepts

### What is Exchange Rate?
The exchange rate is the value of one nation’s currency against another. For example, if 1 USD equals 1.1720 EUR, this is the exchange rate.

### Exchange Rate Example
- If John exchanges $200 at a rate of 1.20, he will get €166.66.
- When exchanging the same €166.66 back to dollars at a reduced rate of 1.15, he would receive $191.67.

---

## Requirements

### Hardware Requirements
- **System**: x86 64-bit CPU (Intel i5 or AMD architecture)
- **RAM**: 8 GB
- **Hard Disk**: 512 GB SSD

### Software Requirements
- **Operating System**: Windows 7/8/10
- **Coding Language**: Python
- **Compiler**: Visual Studio

---

## Implementation

### Steps to Build the Python Project
1. **Real-Time Exchange Rates**: Utilize [ExchangeRate-API](https://api.exchangerate-api.com/v4/latest/USD) for fetching real-time exchange rates.
2. **Import Required Libraries**:
    ```python
    import requests
    from tkinter import *
    import tkinter as tk
    from tkinter import ttk
    ```
3. **CurrencyConverter Class**: Create a class to fetch and handle exchange rate data.
    ```python
    class RealTimeCurrencyConverter():
        def __init__(self, url):
            self.data = requests.get(url).json()
            self.currencies = self.data['rates']
        
        def convert(self, from_currency, to_currency, amount):
            if from_currency != 'USD':
                amount /= self.currencies[from_currency]
            return round(amount * self.currencies[to_currency], 4)
    ```
4. **UI for Currency Converter**: Build the graphical user interface using `tkinter`.
    ```python
    class CurrencyConverterUI(tk.Tk):
        def __init__(self, converter):
            super().__init__()
            self.title = 'Currency Converter'
            self.currency_converter = converter
            # Add UI elements (labels, entry boxes, buttons, etc.) here
    ```
5. **Main Function**:
    ```python
    if __name__ == '__main__':
        url = 'https://api.exchangerate-api.com/v4/latest/USD'
        converter = RealTimeCurrencyConverter(url)
        CurrencyConverterUI(converter).mainloop()
    ```

---

## Conclusion
The Real-Time Currency Converter simplifies currency conversions, providing real-time rates and accurate calculations. Future enhancements could include:
- Support for additional currencies.
- Displaying currency trends and historical rates.

---

## References
- [ExchangeRate API Documentation](https://www.exchangerate-api.com/)
- **Python Libraries**: `tkinter`, `requests`

---

### Developed at R.C.P.I.T, Shirpur

---

**Note**: Contributions, issues, and suggestions are welcome!


# 🌦️ Flask Weather App (Using Your API Key)

## 🎯 Objective

Build a **Weather App using Flask** that fetches real-time weather data using your provided API key.

---

## 📁 Project Structure

```bash
project/
 ├── app.py
 └── templates/
      ├── home.html
      ├── home1.html
      └── home2.html
```

---

## 🧾 1. Backend (`app.py`) ✅

```python
from flask import Flask, render_template, request
import requests

app = Flask(__name__)

@app.route('/', methods=['GET'])
def home():
    return render_template('home.html')


@app.route('/getCity', methods=['POST'])
def getCity():
    city = request.form['city']

    # ✅ Your API Key (used as given)
    api_key = "17b7453a8a96660330b788299e4dfcf3"

    base_url = "http://api.openweathermap.org/data/2.5/weather?"
    complete_url = base_url + "appid=" + api_key + "&q=" + city

    response = requests.get(complete_url)
    x = response.json()

    if x["cod"] != "404":
        y = x["main"]
        sysk = x["sys"]

        dataL = [
            y["temp"],       # Temperature (Kelvin)
            y["pressure"],   # Pressure
            y["humidity"],   # Humidity
            sysk["country"]  # Country
        ]

        return render_template('home1.html', city=city, dataL=dataL)

    else:
        return render_template('home2.html', city=city)


if __name__ == "__main__":
    app.run(debug=True)
```

---

## 🌐 2. `templates/home.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Weather App</title>
</head>
<body>

<h2>🌦️ Weather App</h2>

<form action="/getCity" method="POST">
    <input type="text" name="city" placeholder="Enter city name" required>
    <button type="submit">Search</button>
</form>

</body>
</html>
```

---

## 🌐 3. `templates/home1.html` (Success Page)

```html
<!DOCTYPE html>
<html>
<head>
    <title>Weather Result</title>
</head>
<body>

<h2>Weather for {{city}}</h2>

<p>🌡 Temperature: {{dataL[0]}} K</p>
<p>📊 Pressure: {{dataL[1]}}</p>
<p>💧 Humidity: {{dataL[2]}}</p>
<p>🌍 Country: {{dataL[3]}}</p>

<a href="/">Search Again</a>

</body>
</html>
```

---

## 🌐 4. `templates/home2.html` (Error Page)

```html
<!DOCTYPE html>
<html>
<head>
    <title>Error</title>
</head>
<body>

<h2>❌ City "{{city}}" not found</h2>

<a href="/">Try Again</a>

</body>
</html>
```

---

## ▶️ How to Run

### 🔹 Install dependencies

```bash
pip install flask requests
```

### 🔹 Run app

```bash
python app.py
```

### 🔹 Open in browser

```
http://127.0.0.1:5000/
```

---

## 🔄 Working Flow

1. User enters city
2. Request sent to Flask
3. API is called using your key
4. Data is fetched and displayed
5. Error page shown if city invalid

---

## 💡 Important Note

* Temperature is in **Kelvin (K)**
* To convert to Celsius:

```python
temp_c = y["temp"] - 273.15
```

---

## 🧪 Example Output

* City: Mumbai
* Temperature: 303 K
* Humidity: 70%
* Country: IN

---

## ✅ Conclusion

This project uses your **real API key** and works correctly with Flask + OpenWeather API.

---

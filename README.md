##  Weather-app

Name: HARSHINI R Reg no: 212223220033

Build a Weather App using React

# Objective

Create a simple weather application using React that allows the user to enter a city name and view simulated weather data such as temperature, wind speed, and sky condition.

# Task Description
Develop a weather app that:

Accepts a city name from the user

Displays weather information (temperature, wind speed, sky condition) only for predefined cities

Shows an error message for cities not in the mock data

Requirements
React functional component (WeatherApp)

Text input to enter city name

A button or "Enter" key to trigger search

Display of weather data (if city is valid)

Error message for invalid cities

Basic styling using external or inline CSS

PROGRAM:
```
index.js

import React from 'react';
import ReactDOM from 'react-dom/client';
import './App.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

App.js

import React, { useState } from 'react';

const mockWeatherData = {
  London: {
    temperature: 24,
    windSpeed: 18,
    condition: 'Partly Cloudy ☁️',
  },
  Paris: {
    temperature: 21,
    windSpeed: 12,
    condition: 'Sunny ☀️',
  },
  Tokyo: {
    temperature: 28,
    windSpeed: 15,
    condition: 'Rainy 🌧️',
  },
  Delhi: {
    temperature: 35,
    windSpeed: 10,
    condition: 'Hot 🔥',
  },
};

function App() {
  const [city, setCity] = useState('');
  const [weather, setWeather] = useState(null);

  const handleSearch = () => {
    const formattedCity = city.trim();
    if (formattedCity && mockWeatherData[formattedCity]) {
      setWeather(mockWeatherData[formattedCity]);
    } else {
      setWeather(null);
    }
  };

  return (
    <div className="container">
      <h1>Weather App</h1>
      <div className="search">
        <input
          type="text"
          placeholder="Enter city (e.g. London)"
          value={city}
          onChange={(e) => setCity(e.target.value)}
        />
        <button onClick={handleSearch}>Search</button>
      </div>

      {weather ? (
        <div className="card">
          <h2>{city}</h2>
          <p className="temp">{weather.temperature}°C</p>
          <p>{weather.condition}</p>
          <p>💨 Wind: {weather.windSpeed} km/h</p>
        </div>
      ) : (
        city && <p className="not-found">No weather data found for "{city}"</p>
      )}
    </div>
  );
}

export default App;

App.css

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(to bottom right, #1e3a8a, #6b21a8);
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.container {
  text-align: center;
}

h1 {
  font-size: 3rem;
  margin-bottom: 20px;
}

.search {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 20px;
}

input {
  padding: 10px;
  border-radius: 10px;
  border: none;
  font-size: 16px;
  width: 200px;
}

button {
  padding: 10px 20px;
  background-color: white;
  color: #1e3a8a;
  border: none;
  border-radius: 10px;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #ddd;
}

.card {
  background-color: rgba(255, 255, 255, 0.1);
  padding: 20px;
  border-radius: 20px;
  max-width: 300px;
  margin: 0 auto;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
}

.temp {
  font-size: 2.5rem;
  font-weight: bold;
  margin: 10px 0;
}

.not-found {
  color: #ffcccb;
  font-style: italic;
}

```

# OUTPUT

![image](https://github.com/user-attachments/assets/123d990b-5c40-4dad-9e49-e3bbb1140100)

![image](https://github.com/user-attachments/assets/76a05c31-edc9-45d5-9f98-7268b2553896)

# Result
The given task is implemented by reactor(Weather-app).

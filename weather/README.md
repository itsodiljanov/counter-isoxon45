# 🌤️ Weather Dashboard

A beautiful, responsive weather dashboard built with vanilla JavaScript and the OpenWeather API. Get real-time weather data, hourly forecasts, and 5-day predictions.

## Features

✨ **Current Weather**
- Real-time temperature, humidity, and wind speed
- Weather description and conditions
- "Feels like" temperature
- UV index tracking

📊 **Forecasts**
- Hourly forecast for the next 24 hours
- 5-day weather forecast
- Detailed precipitation and wind information
- Visual weather icons

📍 **Location Features**
- Search for any city worldwide
- Auto-detect user's current location
- Save favorite locations
- Quick access to saved cities

🎨 **User Interface**
- Modern dark theme with gradient backgrounds
- Fully responsive design (mobile, tablet, desktop)
- Smooth animations and transitions
- Clean card-based layout

💾 **Data Management**
- LocalStorage for saving favorites
- API caching (10-minute cache duration)
- Fast load times with intelligent caching

## Getting Started

### 1. Get API Key

1. Visit [OpenWeather API](https://openweathermap.org/api)
2. Sign up for a free account
3. Generate an API key from your account dashboard
4. The free tier includes:
   - Current weather
   - 5-day forecast
   - Hourly forecast
   - Up to 60 calls/minute

### 2. Setup

1. Clone or download this repository
2. Open `weather/config.js`
3. Replace `'YOUR_OPENWEATHER_API_KEY_HERE'` with your actual API key:
   ```javascript
   API_KEY: 'your_actual_api_key_here',
   ```

### 3. Run

Simply open `weather/index.html` in your web browser. No server setup required!

```bash
# If you have Python installed:
python -m http.server 8000
# Then visit http://localhost:8000/weather/index.html

# Or use Node.js:
npx http-server
```

## Usage

### Search for Weather
1. Enter a city name in the search bar
2. Click "Search" or press Enter
3. Weather data loads instantly

### Use Your Location
Click the 📍 button to automatically detect and load weather for your current location (requires permission).

### Save Favorites
When you search for a city, it's automatically added to your "Saved Locations" list. Click a saved location to quickly view its weather.

### Remove Favorites
Click "Remove" on any favorite location card to delete it.

## Project Structure

```
weather/
├── index.html          # Main HTML file with structure
├── styles.css          # Complete styling and responsive design
├── config.js           # Configuration and constants
├── weatherApi.js       # Weather API service class
├── ui.js               # UI management and updates
├── app.js              # Main application logic
└── README.md           # This file
```

## File Descriptions

### index.html
- Contains the HTML structure
- Search interface
- Weather display cards
- Forecast grids
- Favorites section

### styles.css
- Dark theme with gradient backgrounds
- Fully responsive grid layouts
- Smooth animations and transitions
- Card-based design system
- Mobile-optimized (max-width: 480px)

### config.js
- OpenWeather API configuration
- Weapon icons mapping
- Wind direction descriptions
- Temperature thresholds
- Alert configurations

### weatherApi.js
- `WeatherAPI` class handles all API calls
- Current weather fetching
- Forecast retrieval
- Geolocation services
- Reverse geocoding
- Built-in caching system

### ui.js
- `WeatherUI` class manages all UI updates
- Display formatting
- Element references
- Update methods for weather data
- Favorite list management

### app.js
- `WeatherApp` main application class
- Initializes and coordinates all components
- Event listeners setup
- Weather data loading
- Favorites management
- Alert checking

## API Documentation

### OpenWeather Endpoints Used

**Current Weather**
```
GET https://api.openweathermap.org/data/2.5/weather
?lat={lat}&lon={lon}&appid={API_KEY}&units=metric
```

**Forecast (5-day)**
```
GET https://api.openweathermap.org/data/2.5/forecast
?lat={lat}&lon={lon}&appid={API_KEY}&units=metric
```

**Geocoding (City to Coordinates)**
```
GET https://api.openweathermap.org/geo/1.0/direct
?q={city}&limit=1&appid={API_KEY}
```

**Reverse Geocoding (Coordinates to City)**
```
GET https://api.openweathermap.org/geo/1.0/reverse
?lat={lat}&lon={lon}&limit=1&appid={API_KEY}
```

## Configuration Options

Edit `config.js` to customize:

```javascript
// Temperature units
UNITS: 'metric'        // 'metric' = Celsius, 'imperial' = Fahrenheit

// Language
LANG: 'en'             // en, es, fr, de, ru, etc.

// Cache duration
CACHE_DURATION: 600000 // 10 minutes

// Alert thresholds
ALERTS: {
    TEMP_EXTREME_COLD: -10,
    TEMP_EXTREME_HOT: 40,
    WIND_STRONG: 10,
    RAIN_HEAVY: 10,
    UV_DANGEROUS: 8
}
```

## Data Displayed

### Current Weather
- Temperature (with "feels like")
- Weather condition
- Humidity percentage
- Wind speed and direction
- Air pressure
- Visibility distance
- UV index
- Sunrise/Sunset times

### Forecast
- Hourly forecast (next 24 hours)
- 5-day daily forecast
- Precipitation probability
- Wind information
- Weather icons

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Responsive Breakpoints

- **Desktop**: 1200px+
- **Tablet**: 768px - 1200px
- **Mobile**: below 768px
- **Small Phone**: below 480px

## Future Enhancements

- [ ] Weather alerts and notifications
- [ ] Map integration (showing weather across regions)
- [ ] Historical weather data
- [ ] Weather comparison between cities
- [ ] Export weather data as PDF
- [ ] Dark/Light mode toggle
- [ ] Multiple language support
- [ ] Air quality index (AQI)
- [ ] Pollen forecast
- [ ] Weather news feed

## Troubleshooting

### "Please set your OpenWeather API key"
- Make sure you've added your API key to `config.js`
- Check that the API key is valid and active

### Location permission denied
- Allow browser to access your location when prompted
- Or simply search for a city manually

### No data showing
- Check your internet connection
- Verify API key is correct
- Check browser console for errors (F12)
- Ensure API calls aren't being blocked by CORS

### Cached data is old
- Cache duration is set to 10 minutes
- Manually clear by pressing F5 to refresh
- Or clear browser cache

## API Rate Limits

The free OpenWeather API tier allows:
- 60 calls/minute
- 1,000,000 calls/month

## License

MIT - Personal and commercial use

## Author

Created by **Itsodiljanov**

## Resources

- [OpenWeather API Docs](https://openweathermap.org/api)
- [OpenWeather Weather Codes](https://openweathermap.org/weather-conditions)
- [MDN Web Docs](https://developer.mozilla.org/)

## Support

For issues or questions, check the browser console (F12) for error messages.

---

**Happy weather tracking!** 🌞🌧️⛈️

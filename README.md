# Currency Converter - Ionic Angular App

A modern mobile currency converter application built with Ionic Framework and Angular. This app allows users to convert between 25 popular world currencies, view exchange rates, visualize currency trends with charts, and manage favorite currency pairs.

## Features

### 🔄 Currency Converter
- Convert between 25+ popular world currencies
- Real-time exchange rates from ExchangeRate-API
- Automatic conversion as you type
- Swap currencies with one tap
- Add/remove currency pairs to favorites
- Works offline with cached data

### 📊 Exchange Rates
- View current rates for all supported currencies
- Search and filter currencies
- Pull-to-refresh for latest rates
- Base currency selection
- Clean, card-based UI

### 📈 Interactive Charts
- Visualize exchange rate trends over time
- Multiple time periods: 7 days, 30 days
- View minimum, maximum, and average rates
- Responsive Chart.js integration
- Simulated historical data (API limitation)

### ⭐ Favorites
- Save frequently used currency pairs
- Quick access to favorite conversions
- View current rates for favorites
- Swipe to delete
- Navigate directly to converter

### 🌐 Offline Support
- Caches exchange rates locally
- Works without internet connection
- Shows offline indicator
- Automatic sync when online

## Technologies Used

- **Framework**: Ionic 8.0 + Angular 20.0
- **UI Components**: Ionic Angular Components
- **State Management**: RxJS (BehaviorSubject)
- **HTTP Client**: Angular HttpClient
- **Storage**: Capacitor Preferences API
- **Charts**: Chart.js 4.4
- **API**: [ExchangeRate-API](https://api.exchangerate-api.com/)
- **Platform**: Capacitor 7.4

## Supported Currencies

USD, EUR, CZK, GBP, JPY, CHF, CAD, AUD, CNY, INR, RUB, BRL, ZAR, MXN, SGD, HKD, NOK, SEK, DKK, PLN, THB, KRW, TRY, NZD, AED

## Installation

### Prerequisites
- Node.js (v18 or higher)
- npm (v9 or higher)
- Ionic CLI: `npm install -g @ionic/cli`

### Steps

1. Clone the repository or navigate to the project folder:
```bash
cd FinalProject/CurrencyCalc
```

2. Install dependencies:
```bash
npm install
```

3. Run the app in browser:
```bash
ionic serve
```

The app will open in your default browser at `http://localhost:8100`

## Building for Mobile

### Android

1. Add Android platform:
```bash
ionic cap add android
```

2. Build the project:
```bash
ionic build
```

3. Sync with Capacitor:
```bash
ionic cap sync android
```

4. Open in Android Studio:
```bash
ionic cap open android
```

5. Build APK in Android Studio:
- Build > Build Bundle(s) / APK(s) > Build APK(s)
- APK will be generated in `android/app/build/outputs/apk/debug/`

### iOS

1. Add iOS platform:
```bash
ionic cap add ios
```

2. Build and sync:
```bash
ionic build
ionic cap sync ios
```

3. Open in Xcode:
```bash
ionic cap open ios
```

4. Build and run from Xcode

## Project Structure

```
src/
├── app/
│   ├── models/                    # Data models
│   │   ├── currency.model.ts      # Currency interface & constants
│   │   ├── conversion.model.ts    # Conversion history model
│   │   └── rate.model.ts          # Exchange rate response model
│   ├── services/                  # Business logic
│   │   ├── exchange-rate.service.ts   # API communication
│   │   ├── storage.service.ts         # Local storage
│   │   └── favorites.service.ts       # Favorites management
│   ├── pages/                     # Application pages
│   │   ├── converter/             # Main converter page
│   │   ├── rates/                 # Exchange rates list
│   │   ├── chart/                 # Rate trends chart
│   │   └── favorites/             # Saved favorites
│   ├── tabs/                      # Tab navigation
│   ├── app.component.ts           # Root component
│   ├── app.routes.ts              # App routing
│   └── tabs/tabs.routes.ts        # Tab routing
├── environments/                  # Environment configs
├── theme/                         # SCSS theme & variables
└── assets/                        # Static assets
```

## API Usage

The app uses the free ExchangeRate-API:
- **Endpoint**: `https://api.exchangerate-api.com/v4/latest/{currency}`
- **No API key required**
- **Rate limit**: No restrictions on free tier
- **Update frequency**: Data updates daily

### Example Response:
```json
{
  "base": "USD",
  "date": "2024-12-01",
  "time_last_updated": 1701388800,
  "rates": {
    "EUR": 0.92,
    "GBP": 0.79,
    "JPY": 149.52,
    ...
  }
}
```

## Key Features Implementation

### Caching Strategy
- Rates cached for 5 minutes
- Stored in Capacitor Preferences
- Automatic fallback to cache when offline

### Error Handling
- Toast notifications for errors
- Graceful degradation to offline mode
- Retry mechanism built-in

### Responsive Design
- Works on phones (320px+)
- Optimized for common resolutions
- Adaptive layouts for tablets

## Troubleshooting

### Common Issues

**Issue**: App doesn't load exchange rates
- **Solution**: Check internet connection, API might be temporarily down

**Issue**: Charts not displaying
- **Solution**: Ensure Chart.js is installed: `npm install chart.js`

**Issue**: Android build fails
- **Solution**: Check Android SDK is installed and ANDROID_HOME is set

**Issue**: iOS build requires Mac
- **Solution**: iOS development requires Xcode which only runs on macOS

**Issue**: Capacitor sync errors
- **Solution**: Run `npm install` first, then `ionic cap sync`

### Dev Tools

Run with live reload:
```bash
ionic serve --lab
```

View in browser with different device frames:
```bash
ionic serve --devapp
```

Check for errors:
```bash
ionic doctor check
```

## Performance Optimizations

- Lazy loading of pages
- OnPush change detection strategy (can be added)
- Efficient RxJS operators (takeUntil, shareReplay)
- Image and asset optimization
- Service worker for PWA (can be added)

## Future Enhancements

- [ ] Real historical data integration (paid API)
- [ ] Currency conversion calculator history
- [ ] Multiple base currency support
- [ ] Rate change notifications
- [ ] Widget support for Android
- [ ] Dark mode toggle
- [ ] Biometric authentication
- [ ] Export conversion history to CSV
- [ ] Multiple language support (i18n)
- [ ] Cryptocurrency support

## Testing

Run unit tests:
```bash
ng test
```

Run e2e tests:
```bash
ng e2e
```

## License

This project is for educational purposes.

## Author

Created with Ionic Framework and Angular

## Acknowledgments

- Exchange rates provided by [ExchangeRate-API](https://www.exchangerate-api.com/)
- Icons by [Ionicons](https://ionic.io/ionicons)
- Charts by [Chart.js](https://www.chartjs.org/)
- Built with [Ionic Framework](https://ionicframework.com/)

---

**Happy Converting! 💱**

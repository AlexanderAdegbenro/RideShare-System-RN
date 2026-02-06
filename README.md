# RideShare Mobility System (React Native)

**Status:** Architecture Demo
**Tech Stack:** React Native, Redux Toolkit, Google Maps Platform, Tailwind CSS (NativeWind)

## 🚀 Engineering Overview
This project simulates the core logic of a high-frequency mobility application. It focuses on solving specific challenges of **geospatial state management**, **real-time route calculation**, and **complex UI transitions** found in production-grade transportation apps.

![Simulator Screen Shot - iPhone 14 Pro Max - 2023-01-13 at 15 00 58](https://user-images.githubusercontent.com/52863002/212409653-b91b0277-35b1-47d1-bb3d-a1a60ad60a2a.png)
![Simulator Screen Shot - iPhone 14 Pro Max - 2023-01-13 at 15 01 09](https://user-images.githubusercontent.com/52863002/212409675-26c0268c-e67b-4567-972a-6b875713c904.png)
![Simulator Screen Shot - iPhone 14 Pro Max - 2023-01-13 at 15 01 20](https://user-images.githubusercontent.com/52863002/212409688-02ce8c62-c3ac-4e70-b178-c644ad5b9720.png)
![Simulator Screen Shot - iPhone 14 Pro Max - 2023-01-13 at 15 02 17](https://user-images.githubusercontent.com/52863002/212409700-3ac6a38f-c228-46af-94a9-5f70f383f799.png)

## 🛠 Technical Architecture
### 1. Geospatial State Management (Redux Toolkit)
* **Challenge:** Managing complex location states (Origin, Destination, Travel Time) across multiple nested navigators without prop drilling.
* **Solution:** Implemented a global `NavSlice` using **Redux Toolkit** to act as the "Source of Truth" for the user's journey. This allows decoupled components (like the "Ride Options Card") to react instantly to map updates.

### 2. Route Optimization (Google Matrix API)
* Integrated the **Google Directions API** and **Distance Matrix API** to calculate precise travel times and distance-based pricing models in real-time.
* Engineered custom hooks to handle API latency and provide optimistic UI updates while fetching route data.

### 3. Performance & UI
* **Map Rendering:** Optimized `react-native-maps` to handle frequent region changes and marker redrawing without dropping frames.
* **Keyboard Handling:** Utilized `KeyboardAvoidingView` and platform-specific behaviors to ensure seamless input flow on both iOS and Android.

## 📦 Key Features
* **Autocomplete Geocoding:** Real-time location search with debouncing.
* **Dynamic Pricing Engine:** Calculates estimated fares based on distance, time, and simulated "Surge" multipliers.
* **Route Visualization:** Polyline drawing with auto-zoom to fit markers (Origin/Destination) within the viewport.

## ⚠️ Configuration
To run this locally, you must supply your own Google Cloud API Key with Maps SDK enabled.

1.  Clone the repo.
2.  Create a `.env` file in the root directory.
3.  Add your key: `Maps_APIKEY=your_key_here`.
4.  Run `npx expo start`.

---
*Built by Alexander Adegbenro*

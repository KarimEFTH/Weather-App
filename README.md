# Weather App

[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/KarimEFTH/Weather-App)

A simple Android application that displays the current weather conditions for a specified city. It fetches data from the OpenWeatherMap API and presents it in a clean, user-friendly interface.

## Screenshots

<p align="center">
  <img src="https://raw.githubusercontent.com/KarimEFTH/Weather-App/main/image1.PNG" width="300" alt="App Screenshot 1">
  &nbsp; &nbsp; &nbsp;
  <img src="https://raw.githubusercontent.com/KarimEFTH/Weather-App/main/image2.PNG" width="300" alt="App Screenshot 2">
</p>

## Features

*   **Current Weather:** Displays the current temperature, weather status (e.g., "Clear Sky"), and min/max temperatures for the day.
*   **Detailed Information:** Provides details on sunrise/sunset times, wind speed, atmospheric pressure, and humidity.
*   **Dynamic UI:** Shows a loading indicator while fetching data and an error message if the data cannot be retrieved.
*   **Static Location:** The application is currently hardcoded to display weather for Rabat.

## Tech Stack

*   **Language:** Kotlin
*   **Platform:** Android
*   **API:** [OpenWeatherMap API](https://openweathermap.org/api)
*   **Networking:** `AsyncTask` for background network operations.
*   **UI:** Android XML Layouts with a gradient background.
*   **Libraries:**
    *   AndroidX AppCompat
    *   AndroidX Core KTX
    *   Material Components

## Setup and Installation

To get a local copy up and running, follow these simple steps.

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/KarimEFTH/Weather-App.git
    ```
2.  **Open in Android Studio:**
    Open the cloned directory in Android Studio.
3.  **API Key:**
    The project uses a hardcoded API key from OpenWeatherMap. You can find it in `app/src/main/java/com/example/weatherapplication/MainActivity.kt`. It is recommended to replace it with your own key.
    ```kotlin
    val API: String = "YOUR_API_KEY" // Use your API key
    ```
4.  **Build and Run:**
    Build the project and run it on an Android emulator or a physical device.

## Code Overview

The application consists of a single activity, `MainActivity`, which handles the logic for fetching and displaying weather data.

*   **`MainActivity.kt`**: The main screen of the application. It initiates the API call and updates the UI with the fetched data.
*   **`weatherTask`**: An inner class that subclasses `AsyncTask` to perform the network request on a background thread, preventing the UI thread from being blocked.
    *   `doInBackground()`: Builds the API URL and fetches the weather data.
    *   `onPostExecute()`: Parses the JSON response and populates the `TextViews` in the layout with the weather information.
*   **`activity_main.xml`**: The layout file that defines the user interface, including views for temperature, location, and other weather details.

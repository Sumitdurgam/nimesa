# nimesa
Assignment 
import requests

//API_URL = "https://api.example.com/weather"  # Replace with the actual API URL

def get_weather_data(date):
    params = {
        "location": "London",
        "date": date
    }
    response = requests.get(API_URL, params=params)
    data = response.json()
    return data

def print_temperature(date):
    data = get_weather_data(date)
    temperature = data.get("temperature")
    if temperature:
        print(f"Temperature on {date}: {temperature} °C")
    else:
        print(f"No data available for {date}")

def print_wind_speed(date):
    data = get_weather_data(date)
    wind_speed = data.get("wind_speed")
    if wind_speed:
        print(f"Wind Speed on {date}: {wind_speed} m/s")
    else:
        print(f"No data available for {date}")

def print_pressure(date):
    data = get_weather_data(date)
    pressure = data.get("pressure")
    if pressure:
        print(f"Pressure on {date}: {pressure} hPa")
    else:
        print(f"No data available for {date}")

def main():
    while True:
        print("\nMenu:")
        print("1. Get weather")
        print("2. Get Wind Speed")
        print("3. Get Pressure")
        print("0. Exit")
        choice = input("Enter your choice: ")

        if choice == '1':
            date = input("Enter the date (YYYY-MM-DD): ")
            print_temperature(date)
        elif choice == '2':
            date = input("Enter the date (YYYY-MM-DD): ")
            print_wind_speed(date)
        elif choice == '3':
            date = input("Enter the date (YYYY-MM-DD): ")
            print_pressure(date)
        elif choice == '0':
            print("Exiting the program.")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()

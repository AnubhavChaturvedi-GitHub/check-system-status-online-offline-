# is_online Check

## Overview
This simple Python script provides a function `is_online` to check if a given URL is accessible, indicating whether the system is online or offline. It utilizes the `requests` library to make a GET request to the specified URL and checks if the response status code falls within the success range (200-299).

## Requirements
- Python 3.x
- `requests` library (install using `pip install requests`)

## Usage
1. Import the script into your project or copy the code.
2. Ensure the `requests` library is installed (`pip install requests`).
3. Call the `is_online` function with the desired URL and timeout (optional).

```python
import requests

def is_online(url="http://www.google.com", timeout=5):
    try:
        # Try to make a GET request to the specified URL
        response = requests.get(url, timeout=timeout)
        # Check if the response status code is in the success range (200-299)
        return response.status_code >= 200 and response.status_code < 300
    except requests.ConnectionError:
        return False

# Example usage
if is_online():
    print("System is online.")
else:
    print("System is offline.")
```

- The `url` parameter is optional and defaults to "http://www.google.com".
- The `timeout` parameter is optional and defaults to 5 seconds.
- The example usage demonstrates checking if the system is online and prints a corresponding message.

## License
This script is provided under the [MIT License](LICENSE). Feel free to modify and distribute it according to your project requirements.

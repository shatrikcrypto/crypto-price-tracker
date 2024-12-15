# crypto-price-tracker
Це може бути простий інструмент для отримання цін криптовалют через API. 
# Crypto Price Tracker

## Installation
1. Clone the repository:
```bash
git clone https://github.com/yourusername/crypto-price-tracker.git
```

2. Install dependencies:
```bash
pip install requests
```

3. Run the script:
```bash
python tracker.py
```

## Features
- Fetches the current price of Bitcoin, Ethereum, or any cryptocurrency from the CoinGecko API.
- Simple and beginner-friendly.

---

### tracker.py
```python
import requests

def get_crypto_price(crypto_id):
    url = f"https://api.coingecko.com/api/v3/simple/price?ids={crypto_id}&vs_currencies=usd"
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        return data[crypto_id]['usd']
    else:
        return None

def main():
    print("Welcome to Crypto Price Tracker!")
    crypto_id = input("Enter the cryptocurrency (e.g., bitcoin, ethereum): ").lower()
    price = get_crypto_price(crypto_id)

    if price:
        print(f"The current price of {crypto_id.capitalize()} is ${price} USD.")
    else:
        print("Failed to retrieve the price. Please check the cryptocurrency ID.")

if __name__ == "__main__":
    main()
```

### README.md
```markdown
# Crypto Price Tracker

A simple Python tool to fetch cryptocurrency prices using the CoinGecko API.

## How It Works
This script retrieves the current price of a specified cryptocurrency (e.g., Bitcoin, Ethereum) in USD. Users can input the cryptocurrency they want to check, and the script will display the price.

### Requirements
- Python 3.7+
- `requests` library

## Usage
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/crypto-price-tracker.git
    ```
2. Install dependencies:
    ```bash
    pip install requests
    ```
3. Run the script:
    ```bash
    python tracker.py
    ```
4. Enter the name of a cryptocurrency (e.g., bitcoin, ethereum).

## Future Improvements
- Add support for more currencies.
- Display price changes (24h/7d).
- Include a graphical interface.

---
Contributions are welcome! Feel free to fork and submit a pull request.

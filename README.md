import requests
import time

chain = "sepolia"
address = "0x9B5B882369Bb9Ee2Bc00f5C01a48d322355B7DF7"
api_url = f'https://api.chainstack.com/v1/faucet/{chain}'
api_key = "m9d2l4m0.gU0ZpBjBa9ukYmV7A7Ur5v5pGtCABHGX"

def fill_wallet():
    print(f'Sending faucet request for address {address}')
    try:
        response = requests.post(
            api_url,
            json={'address': address},
            headers={
                'Authorization': f'Bearer {api_key}',
                'Content-Type': 'application/json',
            },
        )
        print('API call successful: ', response.json())
    except Exception as error:
        print('Error making API call: ', error)

    time.sleep(24 * 60 * 60)

while True:
    fill_wallet()

<!---
arman2023f/arman2023f is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

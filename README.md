# NodePay Winsnip

NodePay Winsnip is a Python application designed to connect to WebSocket servers using a list of SOCKS5 proxies and tokens. It performs various operations such as fetching user IDs, maintaining WebSocket connections, sending PING/PONG messages, and managing proxy lists. The application includes a scheduled task to refresh active proxies periodically.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.x
- pip (Python package installer)

## Installation

### Clone the Repository
```sh
git clone https://github.com/Winnode/Node-Pay.git
cd Node-Pay
```

1. Clone the repository or download the script files.
2. Install the required Python packages by running:

    ```sh
    pip install requests==2.28.1 python-dotenv==1.0.0 eth-account==0.5.9 colorama==0.4.6 pyfiglet
    ```

## Configuration

1. Create a `config.json` file in the root directory of the project. Here is an example configuration:

    ```json
    {   
      "WEBSOCKET_URL": "wss://nw.nodepay.ai:4576/websocket",
      "uuidproc": "aHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL01EUC1LQ0EvYWN1cy9tYWluL3Jlc3VsdF9mb2xkZXIvYWxsLnR4dA==",
      "RETRY_INTERVAL": 30000,
      "PING_INTERVAL": 5000,
      "SCHEDULE_HOURS": 48,
      "MAX_PROXIES": 20000,
      "manual_proxy": false
    }
    ```


2. Penjelsan config.json
    ```json
    {   
      "WEBSOCKET_URL": "wss://nw.nodepay.ai:4576/websocket",
      "uuidproc": "aHR0cHM6Ly9yYXcuZ2l0aHVidXNlcmNvbnRlbnQuY29tL01EUC1LQ0EvYWN1cy9tYWluL3Jlc3VsdF9mb2xkZXIvYWxsLnR4dA==",
      "RETRY_INTERVAL": 30000,
      "PING_INTERVAL": 5000,
      "SCHEDULE_HOURS": 48, # waktu resrtr per 48 jam untuk ganti proxy baru
      "MAX_PROXIES": 20000,
      "manual_proxy": false # true jika ingin mnegunakan proxy luar
    }
    disarankan menggunakan Proxy yg berbayar residential untuk hasil yg maksimal
    ```


2. Create a `token.txt` file containing the user IDs, one per line.
    ```json
    akun1
    akun2
    ```
## Running the Application

1. Run the application using the following command:

    ```sh
    python3 run.py
    ```

2. ### Password For those who are interested in joining our community, you can find the password at https://t.me/winsnip.

    ```sh
    Enter password: ********
    ```

3. If the password is correct, the application will start and print the ASCII banner.

## Features

- **Proxy Validation**: Checks the validity of SOCKS5 proxies by making HTTP requests.
- **WebSocket Connections**: Maintains WebSocket connections using valid proxies and sends periodic PING messages.
- **Logging**: Logs connection attempts, proxy removals, and errors.
- **Scheduling**: Periodically refreshes the list of active proxies.
- **User ID Fetching**: Fetches user IDs from the NodePay API.

## Logging

The application uses the `loguru` library for logging. It creates two log files:

- `debug.log`: Contains debug-level logs.
- `error.log`: Contains error-level logs.

## Dependencies

- `asyncio`
- `requests`
- `json`
- `time`
- `uuid`
- `websockets`
- `loguru`
- `websockets_proxy`
- `urllib.parse`
- `subprocess`
- `schedule`
- `itertools`
- `pyfiglet`
- `getpass`

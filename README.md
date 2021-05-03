# Fast Test Suite CLI

Fast Test Suite CLI only works with Sandbox environment.

## Prerequisites

#### Python 3
Make sure you have a version of Python 3 installed
```bash
python3 --version
```
You can download the latest version of Python here if you don't have it already: https://www.python.org/downloads/

#### Redis
You will need to install Redis which is in charge of storing your API Access Token securely

macOS
```bash
# Downloads and starts Redis server
brew install redis
brew services start redis
```

Other platforms can navigate to https://redis.io/download for download instructions.
NOTE: You will need to start the redis server in order for the CLI to work.

## Usage

#### Login
To login you will need the API key provided to you and your app id.
This command will store your API key in a local file. Please use logout when finished to remove this file
```bash
./fast-test-suite login
Please enter your API access token: <api_token>
Please enter your app id: <app_id>
```

#### Logout
Logout will remove your API key from the filesystem. Run this once you are done using the CLI.
```bash
./fast-test-suite logout
```

#### PDP Simple New User
```bash
./fast-test-suite pdp-simple-new-user --product-id=<product_id> --app-id=<app_id>
```

#### PDP Simple Existing User
```bash
./fast-test-suite pdp-simple-existing-user --product-id=<product_id> --app-id=<app_id>
```

#### PDP Simple Full Suite
```bash
./fast-test-suite pdp-simple-full-suite --product-id=<product_id> --app-id=<app_id>
```

## Common Issues

#### Initiate Checkout Stage fails
Ensure your product_id that you list exists in your backend.

#### Redis Connection Issue
```bash
Error 61 connecting to localhost:6379. Connection refused.
```
If you see the error above, ensure your local Redis server is running and on port 6379.

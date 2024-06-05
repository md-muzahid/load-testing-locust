# Load Testing with Locust

## Overview
This repository contains the resources and instructions to perform load and stress testing using [Locust](https://locust.io/). The tests were designed to simulate user behavior and measure the performance and scalability of the target system, specifically targeting [CloudNext UK](https://cloudnextuk.co.uk/).

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Setup](#setup)
3. [Running the Tests](#running-the-tests)
4. [Test Scenarios](#test-scenarios)
5. [Interpreting the Results](#interpreting-the-results)
6. [Sample Report](#sample-report)
7. [Contributing](#contributing)
8. [License](#license)

## Prerequisites
Ensure you have the following installed on your system:
- Python 3.7+
- pip (Python package installer)
- Git

## Setup
1. **Clone the repository**:
    ```bash
    git clone https://github.com/md-muzahid/load-testing-locust.git
    cd load-testing-locust
    ```

2. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

## Running the Tests
To run the load tests with Locust, follow these steps:

1. **Start Locust**:
    ```bash
    locust -f locustfile.py
    ```
   By default, Locust will start a web interface at `http://localhost:8089` where you can configure and start the load test.

2. **Configure the Test**:
   - Open the web interface at `http://localhost:8089`.
   - Set the number of total users to simulate.
   - Set the spawn rate (users per second).
   - Enter the host URL of the target system: [https://cloudnextuk.co.uk/](https://cloudnextuk.co.uk/).

3. **Start the Test**:
   - Click the "Start swarming" button to begin the test.
   - Monitor the test progress and results in real-time on the web interface.

## Test Scenarios
The following endpoints of [CloudNext UK](https://cloudnextuk.co.uk/) were tested:
- `GET /item`: Simulates fetching an item.
- `GET //world`: Simulates fetching a world resource.
- `POST //login`: Simulates a user login action.
- `GET //hello`: Simulates fetching a hello resource.

## Interpreting the Results
Here are some key metrics from the sample test run:

- **Average Response Time**: The average time taken for requests to complete.
- **Request Per Second (RPS)**: The number of requests handled by the system per second.
- **Failure Rate**: The percentage of failed requests.
- **95th Percentile Response Time**: The response time below which 95% of the requests fall.

### Sample Results

- **Total Users**: 100
- **Average Response Time**: 247 ms
- **Requests Per Second**: 64.8
- **95th Percentile Response Time**: 280 ms

#### Error Summary
- `GET /item`: 16,133 occurrences of 404 Client Error
- `GET //world`: 575 occurrences of 404 Client Error
- `POST //login`: 99 occurrences of 404 Client Error
- `GET //hello`: 575 occurrences of 404 Client Error

## Sample Report
A detailed report of the test results can be found in the [Locust_Test_Report.html](https://github.com/md-muzahid/load-testing-locust/blob/main/Locust_Test_Report.html).

## Contributing
Contributions are welcome! Please open an issue or submit a pull request with your improvements.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
## Tested By
MD MUZAHID

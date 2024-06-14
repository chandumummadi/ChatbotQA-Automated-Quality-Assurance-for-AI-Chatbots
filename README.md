# Automated Chat Response Validator

This repository contains scripts to automate interactions with both the ZenoChat and HuggingChat platforms, send questions, capture responses, and validate the responses using semantic similarity.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Validation Process](#validation-process)
- [Results Visualization](#results-visualization)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project automates the process of sending questions to ZenoChat and HuggingChat platforms, capturing the responses, and validating the semantic similarity of the responses against expected results. The validation results are saved in Excel files and visualized using pie charts.

## Features

- **Automated Login**: Logs into the ZenoChat and HuggingChat platforms using Selenium WebDriver.
- **Message Sending**: Sends questions from an Excel file to the chat platforms.
- **Response Capture**: Captures responses and saves them in the Excel files.
- **Semantic Validation**: Validates responses using `sentence-transformers` to compare the semantic similarity between expected and actual responses.
- **Results Visualization**: Generates pie charts to visualize the percentage of pass/fail responses.

## Project Structure
```
chat-response-validator/
│
├── ZenoChatTest.py
├── HuggingChatTest.py
├── responseValidator.py
├── requirements.txt
├── README.md
├── ZenoChatResponses.xlsx
└── HuggingChatResponses.xlsx
```

## Prerequisites

- Python 3.x
- Google Chrome browser
- ChromeDriver
- Required Python packages (listed in `requirements.txt`)

## Installation

1. **Clone the repository**:
    ```sh
    git clone https://github.com/chandumummadi/ZenoChat_HuggingChat_UI_Testing.git
    cd automated-chat-response-validator
    ```

2. **Install the required packages**:
    ```sh
    pip install -r requirements.txt
    ```

3. **Download ChromeDriver**:
    Ensure that ChromeDriver is installed and its path is added to the system's PATH variable.

## Usage

### ZenoChat

1. **Update Credentials**:
    - Open `ZenoChatTest.py`.
    - Replace the placeholder email and password with your actual ZenoChat credentials.

2. **Prepare Excel File**:
    - Ensure your Excel file `ZenoChatResponses.xlsx` is structured with questions in the first column and expected responses in the second column.

3. **Run the Script**:
    ```sh
    python ZenoChatTest.py
    ```

4. **Validate Responses**:
    The script will automatically run the validation process after capturing responses.

### HuggingChat

1. **Update Credentials**:
    - Open `HuggingChatTest.py`.
    - Replace the placeholder email and password with your actual HuggingChat credentials.

2. **Prepare Excel File**:
    - Ensure your Excel file `HuggingChatResponses.xlsx` is structured with questions in the first column and expected responses in the second column.

3. **Run the Script**:
    ```sh
    python HuggingChatTest.py
    ```

4. **Validate Responses**:
    The script will automatically run the validation process after capturing responses.

## Validation Process

The validation process involves comparing the actual responses from ZenoChat and HuggingChat with the expected responses using semantic similarity. The `responseValidator.py` script utilizes the `sentence-transformers` library to compute cosine similarity scores between the expected and actual responses. If the similarity score exceeds a specified threshold, the response is marked as "PASS"; otherwise, it is marked as "FAIL".

## Results Visualization

After running the validation, the results are saved back into the respective Excel files, and pie charts are generated to visualize the percentage of pass/fail responses. This helps in understanding the performance of ZenoChat and HuggingChat in providing accurate responses.



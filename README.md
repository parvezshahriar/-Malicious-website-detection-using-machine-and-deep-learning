# Malicious URL Detection

This repository contains a Python project for detecting malicious URLs using various machine learning classification algorithms. The project aims to identify URLs as `benign`, `defacement`, `phishing`, or `malware` based on a set of extracted features.

## Table of Contents

- [Malicious URL Detection](#malicious-url-detection)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Dataset](#dataset)
  - [Features Used](#features-used)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Models Implemented](#models-implemented)
  - [Results](#results)
  - [Dependencies](#dependencies)
  - [Contact](#contact)

## Project Overview

The core idea of this project is to analyze URL characteristics and use machine learning models to classify them into different categories of maliciousness or benign. The process involves:

1.  **Data Loading and Exploration**: Loading the dataset and understanding its structure.
2.  **Feature Engineering**: Extracting various features from the URLs, such as length, special character counts, domain information, and more.
3.  **Data Preprocessing**: Handling categorical data and preparing the dataset for model training.
4.  **Model Training and Evaluation**: Training several classification models and evaluating their performance using accuracy, classification reports, and confusion matrices.

## Dataset

The dataset used is `malicious_phish.csv`, which contains two main columns: `url` and `type`.

| Column | Description                                    |
| :----- | :--------------------------------------------- |
| `url`  | The URL string to be classified.               |
| `type` | The category of the URL (benign, defacement, phishing, malware). |

**Dataset Statistics:**
- Total entries: 651,191
- URL types distribution:
    - `benign`: 428,103
    - `defacement`: 96,457
    - `phishing`: 94,111
    - `malware`: 32,520

## Features Used

The following features are engineered from the raw URLs to train the models:

* **`url_len`**: Length of the URL.
* **`domain`**: The primary domain of the URL.
* **Special Character Counts**: Counts of characters like `@`, `?`, `-`, `=`, `.`, `#`, `%`, `+`, `$`, `!`, `*`, `,`, `//`.
* **`count_www`**: Number of `www` occurrences in the URL.
* **`abnormal_url`**: Indicates if the hostname is found within the URL path (potential abnormality).
* **`https`**: Indicates if the URL uses HTTPS (1 for HTTPS, 0 for HTTP).
* **`digits`**: Number of digits in the URL.
* **`letters`**: Number of letters in the URL.
* **`google_index`**: Checks if the URL appears in Google's search results (a heuristic for legitimacy).
* **`count`**: Number of commas (`,`) in the URL (original code feature).
* **`Shortining_Service`**: Indicates if the URL uses a known URL shortening service.
* **`having_ip_address`**: Detects if the URL contains an IP address instead of a domain name.

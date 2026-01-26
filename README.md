# AWS IAM Rotator 🛡️

A CLI security tool that automates the detection and remediation of duplicate AWS IAM Access Keys. It enforces a safe lifecycle policy (**Deactivate → Verify → Delete**) to ensure compliance with CIS Benchmarks.

## Features

* **Audit Dashboard:** Visualizes all users and key statuses in a color-coded CLI table.
* **Smart Rotation:** Automatically identifies the oldest key in a duplicate pair.
* **Safety Lifecycle:**
  **Run 1:** Deactivates the old key (Safety Mode).
  **Run 2:** Deletes the key *only* if it is already inactive (Cleanup Mode).
* **Self-Preservation:** Built-in logic prevents the script from deactivating the credentials currently running the process.

## Setup

1.  **Clone the repo:**
    ```bash
    git clone [https://github.com/Oluwatobi-Mustapha/aws-iam-rotator.git](https://github.com/Oluwatobi-Mustapha/aws-iam-rotator.git)
    cd aws-iam-rotator
    ```

2.  **Install dependencies:**
    ```bash
    pip install boto3 tabulate colorama
    ```

3.  **Configure AWS:**
    Ensure you have an active session or credentials file.
    if you don't have one, create it in your terminal using:
    ```bash
    aws configure
    ```

##  Usage

   **Run the auditor:**
   ```bash
   python3 audit_keys.py
   ```
 


    
   

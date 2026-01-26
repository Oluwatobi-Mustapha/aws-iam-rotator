# AWS IAM Rotator 🛡️

A CLI security tool that enforces safe AWS IAM access key rotation (Deactivate → Verify → Delete) in alignment with CIS AWS Foundations Benchmarks.

## Features

* **Audit Dashboard:** Visualizes all users and key statuses in a color-coded CLI table.
* **Smart Rotation:** Automatically identifies the oldest key in a duplicate pair.
* **Safety Lifecycle:**
  
  **Run 1:** Deactivates the old key (Safety Mode).
  
  **Run 2:** Deletes the key *only* if it is already inactive (Cleanup Mode).
  
* **Self-Preservation:** Built-in logic prevents the script from deactivating the credentials currently running the process.

## Design Rationale

IAM users can have up to two access keys, which commonly leads to unsafe rotation and long-lived credentials.
This tool enforces a two-phase lifecycle that **deactivates keys before deletion** to reduce blast radius and maintain CIS-aligned key hygiene.

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
    If you don’t have one, create it using:

    ```bash
    aws configure
    ```

##  Usage

   **Run the auditor:**
   ```bash
   python3 audit_keys.py
   ```

**Sample Output:**
<img width="2408" height="907" alt="image" src="https://github.com/user-attachments/assets/679c28e3-e9bc-4db7-ad5a-6463c329b082" />

## ⚠️ Disclaimer
 Use with caution: this tool modifies IAM credentials. Test in non-production or ensure admin console access for recovery.


    
   

# Calculate Client Security Hash

This UiPath project automates the workflow for calculating the Client Security Hash in the ACME System using the **Robotic Enterprise Framework (REFramework)**. It extracts client details from the system, processes the data, generates a secure hash using the SHA1 algorithm, and updates the ACME System1 website with the result.

The use of **REFramework** ensures the project is scalable, reliable, and resilient, with built-in exception handling and logging. The framework manages transactions efficiently, making it suitable for handling large volumes of data.

## Libraries Used

This project uses the following custom libraries:

1. [**ACME System1 Website Library**](https://github.com/mnsy1/UiPath_ACMESystem1): Automates interactions with the ACME System1 website (web automation).
2. **SHA1 Hash Generator**: Handles the secure generation of the client security hash using the SHA1 algorithm.

## Process Workflow

The project follows the **REFramework** approach, with the following steps:

### 1. **Initialization**
- Opens the ACME System1 website in the default browser.
- Reads configuration settings from the `Config.xlsx` file, including system URLs and login credentials asset.
- Initializes the queue for storing work items.

### 2. **Login to ACME System1**
- Log into the ACME System1 website using asset credentials.
- Verifies a successful login before proceeding.

### 3. **Get Transaction Data**
- Navigate to the Work Items page and extract all available work items.
- Each work item represents a transaction that will be processed through the subsequent steps.

### 4. **Process Transaction (REFramework)**

For each work item retrieved, the bot will:
1. **Extract Client Details**: Retrieves the Client ID, Name, and Country from the work item.
2. **Generate Security Hash**: Processes the extracted data to generate a secure hash using the SHA1 algorithm.
3. **Update Work Item**: Submits the security hash and updates the status of the work item on the ACME System1 website.

### 5. **End Process**
- After all transactions are processed, the bot logs out of the ACME System1 website.
- The process gracefully ends, logging completion details.

### 6. **Exception Handling (REFramework)**

- Built-in error handling and retries for any failed transactions.
- Logs detailed error messages for debugging and troubleshooting.

## Conclusion

This project automates the calculation and submission of Client Security Hashes on the ACME System1 platform. Built on the robust UiPath **REFramework**, it ensures reliability, consistency, and scalability. By automating data extraction, secure hash generation, and updating work items, it reduces manual effort and human errors.

## Prerequisites

- **UiPath Studio** (latest version)
- **REFramework Template** preinstalled in UiPath Studio
- **Google Chrome** browser with UiPath extension
- **Valid ACME System1 account credentials**
- **Config.xlsx** file with system credentials asset, URLs, and queue information

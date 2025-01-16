## Overview

This script is designed to set up and manage various background processes for a web service application. It performs tasks such as:

- Checking and creating required directories
- Installing necessary packages
- Authenticating the system
- Downloading necessary files
- Managing GCP Pub/Sub messages
- Sending agent status updates
- Running the main application

## Requirements

- Python 3.x
- Required packages from `requirements.txt`
- Access to GCP for Pub/Sub messages
- Configuration file for the agent

## Script Details

### Libraries Used

- `os`: For interacting with the operating system, such as checking file paths and managing subprocesses.
- `sys`: For system-specific parameters and functions.
- `logging`: For logging information, errors, and application status.
- `multiprocessing`: To manage multiple processes concurrently.
- `subprocess`: To run external commands and manage processes.
- `Event`: A synchronization primitive from the `multiprocessing` library for managing the termination of processes.

### Functions

#### `stop_processes()`

Stops all running processes by:

- Setting the terminate event to stop processes.
- Terminating and waiting for each process to finish.

#### `main_setup()`

Main setup function that performs several tasks:

1. Create Required Directories and Copy Prerequisites:
   Calls the `check_required_dir` function to ensure the necessary directories are created.
2. Install Required Packages:
   Installs the necessary Python packages using the `Installer` class from `utils.installedPackage`.
3. Onboard Token and Fetch Config File:
   Authenticates using the `Board` class from `webservice.onBoard` and fetches the config file.
4. Download Weights:
   Downloads necessary files, such as weights, once the agent is configured using `DownloadWeights`.
5. Handle Pub/Sub Messages:
   Starts a process to listen to GCP Pub/Sub messages using `PubSubListener`.
6. Send Agent Status Every 5 Minutes:
   Starts a process to monitor and send agent status using the `monitor_process` function from `webservice.heartBeat`.
7. Run the Main Application:
   Starts the main application using the `run_app` function from `main.py`.

#### `main` Block

- Runs the `main_setup` function.
- Catches `KeyboardInterrupt` to stop processes and exit gracefully.

## Running the Application

1. Ensure the required directories and files are set up.
2. Install the necessary Python packages using `requirements.txt`.

**Command:**

```bash
python setup.py
```

## Dependencies

- **utils.constantFiles**: Provides constants like the Hawk configuration file path.
- **utils.create_dirs**: Manages directory creation for prerequisites.
- **utils.installedPackage**: Handles package installation from requirements.txt.
- **webservice.onBoard**: Manages onboarding and authentication.
- **helper.downloadWeights**: Manages downloading of necessary weights files.
- **handler.pub_sub_listener**: Listens for messages from Google Cloud Pub/Sub.
- **webservice.heartBea**t: Monitors and sends agent status.
- **main**: Main application logic.

## Logging

- All events are logged using the Python logging module.
- Log messages include information about the processes being started and stopped, errors, and status updates.

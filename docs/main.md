## Purpose

The `main.py` file initializes a Flask web server to provide API routes for managing an agent, handling configurations, and interacting with cameras. It leverages modules such as `lib.agent` and `utils.constantFiles` for functionality.

---

## API

### General

```
GET /
```

Returns a list of all available routes in the application.

---

### Agent Management

#### 1. Get Agent Status

```
GET /agent
```

This API returns the current status of the agent. It helps monitor whether the agent is active, inactive, or encountering any issues.

#### 2. Start Agent

```
POST /agent/start
```

This API starts the agent. Use it to initialize the agent's operations when it is in an inactive state.

#### 3.Stop Agent

```
POST /agent/stop
```

This API stops the agent. It is useful when the agent needs to be paused or shut down for maintenance or troubleshooting.

#### 4.Restart Agent

```
POST /agent/restart
```

This API restarts the agent. If the agent is running, it stops it, waits for 4 seconds, and then starts it again. It ensures a fresh start without manual intervention.

---

### Configuration

#### 1. Agent Configuration

```
GET /agent_config
```

This API returns the current configuration of the agent, allowing you to view the existing settings.

```
POST /agent_config
```

This API creates the agent configuration with the provided JSON if it does not already exist

#### 2. Model Configuration

```
GET /model_config
```

This API retrieves the current configuration of the model, providing insight into its current setup and parameters.

```
POST /model_config
```

This API creates the model configuration with the provided JSON if it does not already exist

---

### Camera Management

#### 1. Get Cameras List

```
GET /cameras
```

This API returns a list of available cameras, including their respective URLs for monitoring and management.

#### 2. Get Camera Details

```
GET /camera/<camera_id>
```

This API returns detailed information about a specific camera, identified by the `camera_id`, allowing you to manage and monitor its settings and status.

---

## Key Components

### 1. Initialization

- Initializes a Flask application instance: `app = Flask(__name__)`.
- Creates an instance of the `Agent` class from `lib.agent`.

### 2. Routes

- Defines multiple routes for agent management, configuration updates, and camera interactions.

### 3. Agent Auto-Start

- If the Hawk configuration file exists (`HawkConfigFile`), the agent auto-starts using the `auto_start_agent()` method during application initialization.

### 4. Graceful Shutdown

- Implements a mechanism to handle keyboard interrupts (`KeyboardInterrupt`) for graceful agent shutdown and server termination.

---

## Running the Application

The application is run using the `run_app()` function, which:

1. Checks for the Hawk configuration file and auto-starts the agent if present.
2. Starts the Flask server on `0.0.0.0` at port `55910`.

**Command:**

```bash
python main.py
```

---

## Error Handling

- Handles errors during server shutdown, particularly when the application is not running with the Werkzeug server.
- Ensures the agent is stopped before exiting on a keyboard interrupt.

---

## Dependencies

- **Flask**: Web framework for Python.
- **lib.agent**: Custom module for agent management.
- **utils.constantFiles**: Provides constants like the Hawk configuration file path.

---

## Notes

- Ensure the required dependencies are installed by running:
  ```bash
  pip install -r requirements.txt
  ```
- Update `HawkConfigFile` and other configurations as needed before starting the server.

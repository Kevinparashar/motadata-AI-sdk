# Core Components

## WHY
The core module provides fundamental building blocks and utilities that are used throughout the SDK. These components establish the foundation for data structures, concurrency handling, event management, and common utilities that other modules depend on.

## WHAT
This module contains:

- **data_structures.py**: Core data models and structures used across the SDK (e.g., request/response models, configuration objects)
- **concurrency.py**: Concurrency utilities for handling asyncio operations, threading, and parallel processing
- **event_handler.py**: Event handling logic for managing SDK events, callbacks, and asynchronous notifications
- **utils.py**: Helper functions for logging, configuration parsing, validation, and other common operations

## HOW
Import and use core components in your code:

```python
from src.core.data_structures import RequestModel, ResponseModel
from src.core.concurrency import AsyncExecutor, ThreadPool
from src.core.event_handler import EventHandler, EventEmitter
from src.core.utils import setup_logger, validate_config
```

These components are typically used internally by other SDK modules, but can also be used directly in your application code when needed.

## Libraries
This module uses the following Python standard libraries and packages:

- **typing**: Type hints for function parameters and return types (Dict, Any, Optional, List, Callable, Coroutine)
- **dataclasses**: Data class decorators for creating structured data models
- **datetime**: Date and time handling for timestamps
- **asyncio**: Asynchronous programming support
- **concurrent.futures**: Thread pool execution (ThreadPoolExecutor, Executor)
- **threading**: Thread synchronization primitives (Thread, Lock)
- **enum**: Enumeration support for event types
- **logging**: Logging framework for application logging
- **os**: Operating system interface for environment variables
- **pathlib**: Object-oriented filesystem paths

## Functions and Classes

### data_structures.py
- **RequestModel** (class): Base request model for API requests with method, URL, headers, params, data, and timestamp
- **ResponseModel** (class): Base response model for API responses with status_code, data, headers, timestamp, and error
- **ConfigModel** (class): Configuration data model with api_url, api_key, timeout, retry_count, and settings

### concurrency.py
- **AsyncExecutor** (class): Async executor for running async functions with event loop management
  - `execute()`: Execute a function asynchronously
  - `run()`: Run a coroutine in the event loop
  - `shutdown()`: Shutdown the executor
- **ThreadPool** (class): Thread pool for parallel execution
  - `submit()`: Submit a task to the thread pool
  - `map()`: Map function over iterable in parallel
  - `shutdown()`: Shutdown the thread pool
- **ThreadSafeCounter** (class): Thread-safe counter with lock protection
  - `increment()`: Increment the counter
  - `decrement()`: Decrement the counter
  - `value` (property): Get the current value

### event_handler.py
- **EventType** (enum): Event type enumeration (INFO, WARNING, ERROR, SUCCESS, CUSTOM)
- **EventHandler** (class): Base event handler for managing events
  - `on()`: Register an event handler
  - `off()`: Unregister an event handler
  - `emit()`: Emit an event
  - `once()`: Register a one-time event handler
- **EventEmitter** (class): Event emitter for asynchronous event handling
  - `on()`: Register an event handler
  - `off()`: Unregister an event handler
  - `emit()`: Emit an event
  - `once()`: Register a one-time event handler

### utils.py
- **setup_logger()**: Setup and configure a logger with custom format and output
- **validate_config()**: Validate configuration dictionary for required keys
- **get_env_var()**: Get environment variable with optional default
- **ensure_dir()**: Ensure directory exists, create if it doesn't
- **merge_dicts()**: Merge multiple dictionaries into one


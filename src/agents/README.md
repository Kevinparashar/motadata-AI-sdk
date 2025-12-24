# Agents Module

## WHY
The agents module enables the creation and management of autonomous AI agents that can communicate, process information, and execute tasks. This module is essential for building agent-based applications that require inter-agent communication and coordination.

## WHAT
This module contains:

- **agent.py**: Main agent class definition that provides the core agent functionality, lifecycle management, and task execution capabilities
- **agent_communication.py**: Communication protocol handlers (e.g., NATS, message queues) for enabling agents to send and receive messages, coordinate tasks, and share information

## HOW
Create and use agents in your application:

```python
from src.agents.agent import Agent
from src.agents.agent_communication import AgentCommunicator

# Create an agent instance
agent = Agent(agent_id="agent-1", capabilities=["task_execution", "data_processing"])

# Set up communication
communicator = AgentCommunicator(protocol="nats")
agent.set_communicator(communicator)

# Start the agent
agent.start()
```

Agents can be configured with specific capabilities, communication protocols, and event handlers to suit your application's needs.

## Libraries
This module uses the following Python standard libraries and packages:

- **typing**: Type hints (List, Dict, Any, Optional, Callable)
- **datetime**: Date and time handling for agent timestamps
- **threading**: Thread synchronization primitives (Lock) for thread-safe operations
- **src.core.event_handler**: EventEmitter and EventType from core module for event handling

## Functions and Classes

### agent.py
- **Agent** (class): Main agent class for autonomous AI agents
  - `__init__()`: Initialize agent with agent_id, capabilities, and config
  - `set_communicator()`: Set the communication handler for the agent
  - `start()`: Start the agent
  - `stop()`: Stop the agent
  - `execute_task()`: Execute a task
  - `_process_task()`: Internal method to process a task
  - `on()`: Register an event handler
  - `send_message()`: Send a message to another agent
  - `receive_message()`: Receive a message from another agent
  - `get_status()`: Get agent status information

### agent_communication.py
- **AgentCommunicator** (class): Base communicator for agent-to-agent communication
  - `__init__()`: Initialize communicator with protocol and config
  - `connect()`: Connect to the messaging system
  - `disconnect()`: Disconnect from the messaging system
  - `send()`: Send a message to a recipient
  - `subscribe()`: Subscribe to a topic
  - `unsubscribe()`: Unsubscribe from a topic
  - `publish()`: Publish a message to a topic
  - `is_connected` (property): Check if connected to messaging system
- **NATSCommunicator** (class): NATS-specific communicator implementation
  - `__init__()`: Initialize NATS communicator with servers
  - `connect()`: Connect to NATS server
  - `send()`: Send message via NATS


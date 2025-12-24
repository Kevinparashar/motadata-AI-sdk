# Metadata Python SDK

## WHY
This SDK provides a comprehensive Python interface for interacting with the Metadata AI platform. It enables developers to build AI-powered applications with agent-based architectures, integrate with multiple AI models, manage database connections, and handle API communications seamlessly. The SDK abstracts away the complexities of AI model integration, database management, and communication protocols, allowing developers to focus on building their applications.

## WHAT
This repository contains the complete source code and documentation for the Metadata Python SDK:

- **src/**: Main source code directory containing all SDK modules
  - **core/**: Core components and utilities (data structures, concurrency, event handling, utils)
  - **agents/**: Agent-related functionality for autonomous AI agents
  - **ai_gateway/**: AI Gateway components for model integration
  - **database/**: Database integrations (SQL, NoSQL, Vector DB)
  - **codecs/**: Custom encoding and decoding logic
  - **api/**: API communication and authentication
  - **config/**: Configuration management and logging
  - **tests/**: Unit tests for all SDK components
- **requirements.txt**: Python package dependencies
- **setup.py**: Python setup file for package installation
- **LICENSE**: License information for the SDK

## HOW
### Installation
Install the SDK using pip:

```bash
pip install -r requirements.txt
```

Or install in development mode:

```bash
pip install -e .
```

### Basic Usage
Import and use SDK components:

```python
from src.agents.agent import Agent
from src.ai_gateway.gateway import AIGateway
from src.database.sql_db import SQLDatabase
from src.api.api_communicator import APICommunicator

# Initialize components
agent = Agent(agent_id="my-agent")
gateway = AIGateway(provider="openai", api_key="your-key")
db = SQLDatabase(connection_string="postgresql://...")
api = APICommunicator(base_url="https://api.example.com")
```

### Getting Started
1. Review the README.md files in each module directory for specific usage instructions
2. Check `src/config/README.md` for configuration setup
3. Explore `src/tests/` for usage examples in test files
4. Refer to individual module documentation for detailed API references

For detailed information about each module, see the README.md files in their respective directories.

## Libraries
The SDK uses Python standard library modules and will support third-party packages as needed:

**Python Standard Library:**
- **typing**: Type hints for better code documentation and IDE support
- **dataclasses**: Data class decorators for structured data models
- **datetime**: Date and time handling
- **asyncio**: Asynchronous programming support
- **threading**: Thread synchronization and parallel execution
- **enum**: Enumeration support
- **logging**: Logging framework
- **os**: Operating system interface
- **pathlib**: Object-oriented filesystem paths
- **json**: JSON encoding and decoding
- **base64**: Base64 encoding and decoding
- **abc**: Abstract base classes
- **concurrent.futures**: Thread pool execution
- **unittest**: Unit testing framework

**Third-party Libraries:**
- (Add third-party dependencies as they are added to requirements.txt)

## Functions and Classes
The SDK is organized into modules, each containing specific functions and classes:

### Core Module (`src/core/`)
- **Data Models**: RequestModel, ResponseModel, ConfigModel
- **Concurrency**: AsyncExecutor, ThreadPool, ThreadSafeCounter
- **Events**: EventHandler, EventEmitter, EventType
- **Utilities**: setup_logger, validate_config, get_env_var, ensure_dir, merge_dicts

### Agents Module (`src/agents/`)
- **Agent**: Main agent class with lifecycle management
- **AgentCommunicator**: Base communicator for agent-to-agent communication
- **NATSCommunicator**: NATS-specific communicator implementation

### AI Gateway Module (`src/ai_gateway/`)
- **AIGateway**: Main gateway interface for AI model interactions
- **ModelProvider**: Abstract base class for model providers
- **OpenAIProvider, AnthropicProvider**: Specific model provider implementations
- **PromptManager, PromptTemplate**: Prompt management system
- **I/O Functions**: preprocess_input, postprocess_output, normalize_text, chunk_text, format_messages

### Database Module (`src/database/`)
- **SQLDatabase**: SQL database connection and operations (PostgreSQL, MySQL)
- **NoSQLDatabase**: NoSQL database operations (MongoDB, Cassandra)
- **VectorDatabase**: Vector database for similarity search (FAISS, Pinecone)

### Codecs Module (`src/codecs/`)
- **Codec**: Abstract base class for codecs
- **JSONCodec, Base64Codec, BinaryCodec, CustomCodec**: Specific codec implementations
- **Utilities**: register_codec, get_codec, list_codecs, validate_encoded_data, encode_with_format, decode_with_format

### API Module (`src/api/`)
- **APICommunicator**: HTTP and WebSocket communication
- **WebSocketCommunicator**: Real-time WebSocket communication
- **Authenticator**: Base authenticator class (OAuth2, JWT, APIKey implementations)
- **Utilities**: encode_data, decode_data, send_request, prepare_request_data, parse_response

### Config Module (`src/config/`)
- **Settings**: Configuration settings manager
- **LoggerMixin**: Mixin class for logging capability
- **Functions**: load_config, setup_logger, get_logger, configure_logging

### Tests Module (`src/tests/`)
- **Test Classes**: TestAgent, TestAgentCommunicator, TestAIGateway, TestPromptManager, TestSQLDatabase, TestNoSQLDatabase, TestVectorDatabase, TestJSONCodec, TestBase64Codec, TestCustomCodec, TestAPICommunicator, TestOAuth2Authenticator, TestJWTAuthenticator, TestAPIKeyAuthenticator

For detailed function and class documentation, refer to the README.md files in each module directory.


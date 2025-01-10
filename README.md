# MCP Kafka Processor

An MCP server implementation that provides event processing capabilities through Kafka integration. This server allows Large Language Models to interact with Kafka topics through the Model Context Protocol.

## Features

- Publish events to Kafka topics
- Consume events from Kafka topics
- Easy integration with Claude Desktop and other MCP clients
- Type-safe implementation using TypeScript

## Prerequisites

- Node.js 16 or higher
- Kafka broker accessible
- TypeScript knowledge for development

## Installation

```bash
# Clone the repository
git clone https://github.com/boufnichel/mcp-kafka-processor.git
cd mcp-kafka-processor

# Install dependencies
npm install

# Build the project
npm run build
```

## Configuration

The server can be configured using environment variables:

- `KAFKA_BROKERS`: Comma-separated list of Kafka brokers (default: "localhost:9092")

## Usage with Claude Desktop

Add the following to your Claude Desktop configuration (`claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "event-processor": {
      "command": "node",
      "args": ["/absolute/path/to/build/index.js"],
      "env": {
        "KAFKA_BROKERS": "localhost:9092"
      }
    }
  }
}
```

## Available Tools

### publish-event

Publishes a message to a specified Kafka topic.

Parameters:
- `topic`: The Kafka topic to publish to
- `message`: The message content to publish
- `key`: Optional message key

### consume-events

Consumes messages from a specified Kafka topic.

Parameters:
- `topic`: The Kafka topic to consume from
- `maxMessages`: Maximum number of messages to consume (default: 10)

## Development

```bash
# Install dependencies
npm install

# Build the project
npm run build

# Start the server
npm start
```

## License

MIT
# MqttDistribNet: Simplifying AMQP Messaging with Structured Distribution

**Author:** [Tjark Prokoph](https://github.com/tjarkpr)  
**Repository:** [github.com/tjarkpr/mqttdistribnet](https://github.com/tjarkpr/mqttdistribnet)

## Overview

MqttDistribNet is a Go-based library designed to streamline the management and usage of AMQP brokers, such as RabbitMQ. It introduces a structured approach to configuring messaging infrastructures and facilitates message distribution through intuitive patterns.

## Core Concepts

### 1. Dynamic Infrastructure Management

Managing AMQP infrastructures can be complex, especially when dealing with numerous topics, queues, and bindings. MqttDistribNet addresses this by introducing two key interfaces:

- **`IDistributionNetworkManager`**: Acts as the server-side component responsible for managing the messaging infrastructure. It handles the configuration of topics, queues, and their bindings in a logical and organized manner.

- **`IRemoteDistributionNetworkManager`**: Serves as the client-side counterpart, allowing clients to retrieve information about the remotely managed infrastructure. This facilitates dynamic adjustments and ensures consistency across distributed systems.

### 2. Simple Message Distribution

Building upon established messaging patterns, MqttDistribNet provides abstractions to simplify message handling:

- **Handlers**: Define the logic to process incoming messages.

- **Consumers**: Listen to specific queues and delegate messages to the appropriate handlers.

- **Clients**: Send messages following either the Request/Response or Publish/Subscribe patterns, targeting specific message types configured within the infrastructure.

This structured approach ensures that message distribution is both efficient and maintainable.

## Getting Started

To integrate MqttDistribNet into your Go project:

1. **Import the package**:

   ```go
   import (
       mqttdistribnet "github.com/tjarkpr/mqttdistribnet/pkg"
       amqp "github.com/rabbitmq/amqp091-go"
   )
   ```


2. **Set up the Distribution Network Manager**:

   Initialize the `IDistributionNetworkManager` to configure your messaging infrastructure.

3. **Implement Handlers and Consumers**:

   Define handlers for your message types and set up consumers to listen to the appropriate queues.

4. **Utilize Clients for Messaging**:

   Use the provided client abstractions to send and receive messages following your desired patterns.

For detailed examples and advanced configurations, refer to the repository's [README](https://github.com/tjarkpr/mqttdistribnet/blob/dev/README.md).

## Repository Structure

- **`pkg/`**: Contains the core library code, including interfaces and implementations for infrastructure management and message distribution.

- **`tests/`**: Houses test cases to ensure the reliability and correctness of the library's functionalities.

- **`go.mod` & `go.sum`**: Define the module's dependencies and their versions.

## Contributing

Contributions are welcome! If you encounter issues or have suggestions for improvements, feel free to open an issue or submit a pull request on the [GitHub repository](https://github.com/tjarkpr/mqttdistribnet).

## License

MqttDistribNet is released under the MIT License. For more details, refer to the [LICENSE](https://github.com/tjarkpr/mqttdistribnet/blob/dev/LICENSE) file in the repository.

---

By providing structured management and simplified message distribution, MqttDistribNet aims to enhance the developer experience when working with AMQP messaging systems.
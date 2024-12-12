# WebSocket Ticket Selling System

## Overview
This is a distributed ticket selling system built with Spring Boot and WebSocket technology. The system simulates a ticket marketplace where vendors release tickets and customers purchase them in a concurrent environment.

## Features
- Real-time ticket pool updates via WebSocket
- Configurable ticket release and customer retrieval rates
- Concurrency management for ticket sales
- WebSocket and REST API endpoints for system control

## System Components
- **Vendor**: Releases tickets into the ticket pool
- **Customer**: Retrieves and purchases tickets
- **TicketPool**: Manages ticket availability and transactions
- **WebSocket Configuration**: Enables real-time communication

## Prerequisites
- Java 17 or higher
- Maven
- Spring Boot 3.x
- WebSocket support
- A compatible frontend application (Angular recommended)

## Installation

### Backend Setup
1. Clone the repository
   ```bash
   git clone https://github.com/your-username/ticket-selling-system.git
   cd ticket-selling-system
   ```

2. Build the project
   ```bash
   mvn clean install
   ```

3. Run the application
   ```bash
   mvn spring-boot:run
   ```

### Frontend Requirements
- Use a WebSocket-compatible client (recommended: Angular)
- Configure WebSocket endpoint: `ws://localhost:8080/chat`

## Configuration Endpoints

### REST Configuration Endpoints
- `GET /config/previous`: Retrieve previous configuration
- `POST /config/setup`: Set up system parameters
- `POST /config/start`: Start the ticket selling system
- `POST /config/stop`: Stop the ticket selling system

### Configuration Parameters
- `maxTicketCapacity`: Maximum number of tickets to be sold
- `totalTickets`: Initial number of tickets
- `ticketReleaseRate`: Interval between ticket releases (milliseconds)
- `customerRetrievalRate`: Interval between customer ticket purchases (milliseconds)

## WebSocket Messaging
- Ticket pool updates: `/topic/ticket-pool`
- Messages: `/topic/messages`
- Sending messages: `/app/sendMessage`

## Example Configuration Request
```json
{
  "maxTicketCapacity": 100,
  "totalTickets": 50,
  "ticketReleaseRate": 1000,
  "customerRetrievalRate": 500
}
```

## System Workflow
1. Configure system parameters via REST endpoint
2. Start the system
3. Vendors begin releasing tickets
4. Customers start purchasing tickets
5. Real-time updates via WebSocket

## Security Considerations
- Configured CORS for `localhost` and `127.0.0.1`
- Implement additional security measures for production

## Troubleshooting
- Ensure all configuration values are positive
- Check network connectivity
- Verify WebSocket connection
- Monitor server logs

## Contributing
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.

## Author
Sandil Peiris

## Support
For support, please open an issue in the GitHub repository.

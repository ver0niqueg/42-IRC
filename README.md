# GITIRC 💬

GITIRC is an IRC (Internet Relay Chat) server implementation that demonstrates network programming concepts. It helps understand the following concepts: socket programming, client-server architecture, event handling, command processing, and multi-client connection management.

## Table of contents

- [Highlights](#highlights)
- [Functions](#functions)
- [Definitions](#definitions)
- [Installation](#installation)
- [Usage](#usage)
- [Commands](#commands)

## Highlights

- Full-featured IRC server supporting multiple concurrent clients
- Channel management with operator privileges
- User authentication and registration
- Real-time message broadcasting
- Support for private messages between users
- Channel topic management and member listing
- Kick and ban functionality for operators
- Numeric reply system compliant with IRC standards
- Event-driven architecture for efficient connection handling

## Definitions

| Term | Description |
|------|-------------|
| IRC | Internet Relay Chat, a protocol for real-time text messaging |
| Client | A program connecting to the IRC server |
| Channel | A chat room where multiple users can communicate |
| Operator | A user with elevated privileges in a channel |
| Numeric Reply | Standardized response codes following RFC 1459 |
| Socket | An endpoint for network communication |
| Event Loop | Continuous monitoring of client connections and incoming messages |
| Command Handler | System that processes and executes IRC commands |

## Functions

### Core Functions

**Server**: Main server class managing connections, channels, and the event loop

**Client**: Represents a connected user with authentication status, username, and channel membership

**Channel**: Manages channel membership, messages, operators, and channel-specific settings

**CommandHandler**: Processes incoming IRC commands and routes them to appropriate handlers

**AuthCommands**: Handles PASS, NICK, and USER commands for client registration

**ChannelCommands**: Processes JOIN, PART, LIST, and channel management commands

**MessageCommands**: Handles PRIVMSG and NOTICE for sending messages

**OperatorCommands**: Processes KICK, BAN, TOPIC, and operator-specific functions

**handle_client_input**: Parses incoming client messages and triggers command execution

**broadcast_message**: Sends messages to all users in a channel

**validate_nickname**: Ensures nickname uniqueness and validity

## Installation

Clone the repository:
```bash
git clone git@github.com:ver0niqueg/42-IRC.git
cd 42-IRC
```

Compile:
```bash
make
```

Clean object files:
```bash
make clean
```

Remove all generated files:
```bash
make fclean
```

## Usage

Run the server with a port number:
```bash
./ircserv <port>
```

Example:
```bash
./ircserv 6667
```

Connect with an IRC client:
```bash
nc localhost 6667
```

Or use a dedicated IRC client like `irssi` or `weechat`:
```bash
irssi -c localhost -p 6667
```

## Commands

### User Commands

- **PASS <password>**: Authenticate with server password
- **NICK <nickname>**: Set or change your nickname
- **USER <username> <hostname> <servername> <realname>**: Register user information
- **JOIN <channel>**: Join a channel
- **PART <channel>**: Leave a channel
- **PRIVMSG <target> <message>**: Send a private message
- **NOTICE <target> <message>**: Send a notice message
- **LIST**: List all available channels
- **NAMES <channel>**: List users in a channel
- **TOPIC <channel> [topic]**: View or set channel topic

### Operator Commands

- **KICK <channel> <user> [reason]**: Remove a user from channel
- **MODE <channel> <modes>**: Modify channel modes
- **INVITE <user> <channel>**: Invite user to channel

### Server Commands

- **QUIT**: Disconnect from server
- **PING**: Test connection
- **PONG**: Respond to PING

## Configuration

The server expects:
- A valid port number (typically 6667 for IRC)
- An optional server password for user authentication
- Client connections via TCP sockets

## IRC Compliance

This implementation follows RFC 1459 (Internet Relay Chat Protocol) standards for:
- Numeric reply codes (001-999)
- Command syntax and format
- Message structure and parsing

---

vgalmich & cldalmaz

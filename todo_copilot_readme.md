# TODO Copilot 🤖

A powerful AI-powered personal assistant built with n8n that helps you manage your daily life tasks through natural language conversations. Connect with your TODO Copilot via Telegram to effortlessly manage emails, create calendar events, track expenses, and organize your Microsoft To Do tasks.

## ✨ Features

- **🔄 Smart Task Management**: Create, read, update, and delete tasks in Microsoft To Do
- **📧 Email Management**: Get emails, create drafts, mark as read/unread through Gmail integration
- **📅 Calendar Management**: Create events with attendees, get upcoming events, update and delete calendar entries
- **💰 Expense Tracking**: Store and manage your expenses in Airtable
- **🤖 Natural Language Processing**: Powered by Groq's AI models (GPT-OSS-120B and GPT-OSS-20B) for intelligent conversation
- **📱 Telegram Interface**: Easy-to-use chat interface for all interactions
- **🔄 Automated Workflows**: Intelligent routing and error handling across all operations

## 🏗️ Architecture

The system consists of several specialized agents:

- **Ultimate Assistant**: Main orchestrator that routes requests to appropriate agents
- **TODO Agent**: Manages Microsoft To Do tasks
- **Calendar Agent**: Handles calendar events and meetings
- **Email Agent**: Processes Gmail operations
- **Database Agent**: Manages expense records in Airtable
- **Groq Chat Model**: Provides AI-powered natural language understanding

## 🛠️ Technology Stack

- **Automation Platform**: n8n
- **AI Engine**: Groq (GPT-OSS-120B, GPT-OSS-20B)
- **Chat Interface**: Telegram Bot API
- **Email**: Gmail API
- **Calendar**: Google Calendar API
- **Task Management**: Microsoft To Do API
- **Database**: Airtable

## 📋 Prerequisites

Before setting up TODO Copilot, you'll need to obtain the following API credentials:

### Required API Keys & Tokens

1. **Telegram Bot Token**
   - Create a new bot via [@BotFather](https://t.me/botfather)
   - Save the bot token

2. **Gmail API Credentials**
   - Enable Gmail API in Google Cloud Console
   - Create OAuth 2.0 credentials
   - Download the credentials file

3. **Google Calendar API**
   - Enable Calendar API in Google Cloud Console
   - Use the same OAuth credentials as Gmail

4. **Microsoft To Do Credentials**
   - Register an application in Azure AD
   - Get client ID and client secret
   - Configure appropriate permissions

5. **Airtable Access Token**
   - Generate personal access token from Airtable
   - Note your base ID and table names

6. **Groq API Key**
   - Sign up at [Groq](https://groq.com)
   - Generate API key for model access

## 🚀 Installation

### 1. n8n Setup

```bash
# Install n8n globally
npm install n8n -g

# Or using Docker
docker run -it --rm --name n8n -p 5678:5678 n8nio/n8n
```

### 2. Import Workflows

1. Download the workflow files from this repository
2. Open n8n interface (http://localhost:5678)
3. Import each workflow:
   - Main TODO Copilot workflow
   - TODO Agent workflow
   - Calendar Agent workflow
   - Email Agent workflow
   - Database Agent workflow

### 3. Configure Credentials

In n8n, set up the following credentials:

#### Telegram Bot
- **Name**: `telegram_bot`
- **Access Token**: Your Telegram bot token

#### Gmail OAuth2
- **Name**: `gmail_oauth`
- **Client ID**: From Google Cloud Console
- **Client Secret**: From Google Cloud Console
- **Scope**: `https://www.googleapis.com/auth/gmail.readonly https://www.googleapis.com/auth/gmail.modify`

#### Google Calendar OAuth2
- **Name**: `calendar_oauth`
- **Client ID**: Same as Gmail
- **Client Secret**: Same as Gmail
- **Scope**: `https://www.googleapis.com/auth/calendar`

#### Microsoft Graph OAuth2
- **Name**: `microsoft_oauth`
- **Client ID**: From Azure AD
- **Client Secret**: From Azure AD
- **Scope**: `https://graph.microsoft.com/Tasks.ReadWrite`

#### Airtable API
- **Name**: `airtable_api`
- **API Key**: Your Airtable personal access token
- **Base ID**: Your Airtable base ID

#### Groq API
- **Name**: `groq_api`
- **API Key**: Your Groq API key

### 4. Activate Workflows

1. Enable all imported workflows
2. Test the Telegram webhook connection
3. Send a test message to your bot

## 💬 Usage

### Getting Started

1. Start a chat with your Telegram bot
2. Send any message to begin interaction
3. The AI assistant will understand and route your requests automatically

### Example Commands

#### Task Management
```
"Add a task to buy groceries tomorrow"
"Show me my pending tasks"
"Mark 'call dentist' as completed"
"Delete the meeting task"
```

#### Calendar Management
```
"Schedule a meeting with John at 3 PM tomorrow"
"What's on my calendar this week?"
"Create a dinner event for Friday at 7 PM"
"Cancel my 2 PM meeting today"
```

#### Email Management
```
"Check my recent emails"
"Create a draft email to sarah@example.com about project updates"
"Mark all emails from boss as read"
```

#### Expense Tracking
```
"Add expense: $25 for lunch"
"Record $100 spent on groceries"
"Show my expenses for this month"
```

## 🔧 Configuration

### Customizing Agents

Each agent can be customized by modifying its workflow:

- **Response Templates**: Edit the message formats in each agent
- **Error Handling**: Modify the retry logic and error messages
- **AI Prompts**: Adjust the system prompts for better responses
- **Field Mappings**: Change how data is stored and retrieved

### Adding New Features

To extend functionality:

1. Create new tool nodes in the Ultimate Assistant
2. Build corresponding agent workflows
3. Update the AI routing logic
4. Test the new integration

## 🐛 Troubleshooting

### Common Issues

**Bot Not Responding**
- Check Telegram webhook configuration
- Verify bot token is correct
- Ensure n8n workflows are active

**Authentication Errors**
- Refresh OAuth tokens
- Check API key validity
- Verify credential scopes

**AI Responses Unclear**
- Review system prompts
- Check Groq API quota
- Validate model parameters

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Built with [n8n](https://n8n.io/) automation platform
- Powered by [Groq](https://groq.com) AI inference
- Integrates with Microsoft, Google, and Airtable APIs

---

**Made with ❤️ for personal productivity**
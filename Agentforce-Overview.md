# Agentforce Overview: Topics, Actions, and Agent Types

## Table of Contents
- [What is Agentforce?](#what-is-agentforce)
- [Agent Types](#agent-types)
- [Topics](#topics)
- [Actions](#actions)
- [Prompts and Templates](#prompts-and-templates)
- [Best Practices](#best-practices)

---

## What is Agentforce?

Agentforce is Salesforce's autonomous AI agent platform that enables businesses to deploy AI agents capable of performing tasks independently across sales, service, marketing, and commerce functions. Unlike traditional AI assistants or copilots, Agentforce agents can act almost autonomously, making decisions, automating workflows, and taking actions across multiple systems.

**Key Characteristics:**
- High degree of autonomy with minimal human input
- Independent action-taking capabilities
- Automated workflow execution
- Multi-system decision-making
- Built on the Einstein AI platform

---

## Agent Types

Agentforce provides seven out-of-the-box agent types, plus the ability to create custom agents:

### Sales Agents

#### 1. Sales Development Representative (SDR)
**Purpose:** Autonomous lead engagement and qualification

**Capabilities:**
- Engages with inbound leads autonomously
- Answers product questions
- Handles objections
- Qualifies and nurtures leads
- Books meetings with sales representatives
- Converts prospects into customers

#### 2. Sales Coach
**Purpose:** Real-time sales team support

**Capabilities:**
- Provides tips and insights to sales teams
- Offers real-time coaching during sales processes
- Helps sellers role-play different sales scenarios
- Supports deal closure strategies

---

### Service Agents

#### 3. Service Agent
**Purpose:** 24/7 customer support and issue resolution

**Capabilities:**
- Resolves routine billing questions
- Performs general troubleshooting
- Handles appointment scheduling
- Manages case resolution
- Autonomously resolves customer inquiries
- Tracks customer issues
- Escalates to human representatives when necessary
- Identifies and addresses customer dissatisfaction through sentiment analysis

---

### Commerce Agents

#### 4. Merchant Agent (Merchandiser)
**Purpose:** Commerce operations management

**Capabilities:**
- Tracks stock levels
- Processes orders
- Updates product catalogs
- Manages product listings
- Controls pricing

#### 5. Buyer Agent
**Purpose:** Customer purchasing assistance

**Capabilities:**
- Helps customers find products
- Compares products
- Assists with purchase decisions
- Provides buying guidance

#### 6. Personal Shopper
**Purpose:** Personalized shopping experience

**Capabilities:**
- Offers personalized product suggestions
- Recommends products based on customer preferences
- Provides tailored shopping experiences
- Creates customized product recommendations

---

### Marketing Agents

#### 7. Campaign Optimizer
**Purpose:** Marketing campaign enhancement

**Capabilities:**
- Generates campaign briefs
- Creates target audience segments
- Develops marketing campaigns
- Generates marketing content
- Designs customer journeys
- Helps marketing teams plan effective campaigns

---

### Custom Agents

#### 8. Agent Builder (Custom Solutions)
**Purpose:** Tailored business-specific agents

**Capabilities:**
- Fully customizable agents for unique business needs
- Low-code development tools
- Can be built for any of the five agent categories:
  - Service Agents
  - Sales Agents
  - Marketing Agents
  - Commerce Agents
  - Platform Agents

---

## Topics

Topics are categories that group related tasks an agent can handle. They categorize the "Job To Be Done" and define an agent's role by guiding it to apply the right instructions and actions during a conversation.

### Topic Components

Each topic includes:
1. **Classification Description**: Determines if this is the correct topic based on user intent
2. **Scope**: Defines exactly what an agent can do when this topic is being used
3. **Actions**: Tools used to complete the tasks
4. **Instructions**: Guidance that helps the agent make decisions

### Standard Topics

Agentforce provides standard topics for common use cases across different domains:

#### Service Topics
- **Case Management**: Handle customer support cases from creation to resolution
- **Appointment Scheduling**: Schedule, reschedule, and cancel service appointments
- **Order Inquiries**: Answer questions about order status and tracking
- **Account Management**: Manage customer account information and settings
- **Delivery Issues**: Address delivery problems and delays
- **General FAQs**: Answer frequently asked questions
- **Reservation Management**: Handle bookings, modifications, and cancellations
- **Billing Support**: Resolve routine billing questions
- **Escalation**: Handle agent-to-human transfers when customers request to speak with a human agent
  - Includes classification description to determine when to escalate
  - Manages handoff process from AI to human agents
  - Transfers conversation context seamlessly to live agents
  - Triggers based on complexity threshold, sensitive topics, or customer requests

#### Sales Topics
- **Lead Qualification**: Assess and qualify potential leads
- **Meeting Scheduling**: Book meetings between prospects and sales reps
- **Product Information**: Provide details about products and services
- **Objection Handling**: Address customer concerns and objections

#### Commerce Topics
- **Product Catalog Management**: Update and maintain product listings
- **Inventory Management**: Track and manage stock levels
- **Order Processing**: Process customer orders
- **Price Management**: Update and control product pricing

#### Marketing Topics
- **Campaign Creation**: Generate campaign briefs and content
- **Audience Segmentation**: Create and manage target audience segments
- **Customer Journey Design**: Map and optimize customer experiences

#### Universal/Platform Topics (Agentforce 2.0)
- **Fallback**: Captures and handles queries not covered by specific topics
  - Ensures users get answers from Salesforce documentation when no direct topic match is found
  - Prevents dead ends in conversations
  - Provides graceful handling of unexpected queries
  - New feature in Agentforce 2.0

- **Object Management**: Empowers admins to quickly identify objects and fields
  - Saves time when making configuration changes
  - Helps troubleshoot data issues
  - Provides insights into Salesforce data structure
  - New feature in Agentforce 2.0

#### Field Service Topics
- **Field Service Dispatcher Actions**: Manage field service operations and dispatch workflows

### Custom Topics

Organizations can create custom topics to address specific business needs beyond the standard offerings.

**Best Practice:** Assign no more than 15 actions to a topic for optimal performance.

---

## Actions

Actions define the specific tasks an agent can perform based on the selected topic. Multiple actions can be triggered simultaneously depending on the topic and instructions.

### Standard Actions

Agentforce provides approximately 30 out-of-the-box standard actions for common tasks:

#### Knowledge & Information
- **Answer Questions with Knowledge**: Leverages Salesforce Data Cloud to search and retrieve knowledge articles
- **Search Knowledge Base**: Find relevant articles and documentation
- **Get Record Details**: Retrieve specific record information

#### Data Operations
- **Query Records**: Search and retrieve records from Salesforce
- **Query Records with Aggregate**: Perform data aggregation tasks
- **Identify a Record**: Locate specific records based on criteria
- **Identify Object**: Identify Salesforce objects and their properties
- **Create Record**: Create new records in Salesforce (available via Flow actions)
- **Update Record**: Update existing records and their custom fields

#### Communication & Documentation
- **Draft an Email**: Create email content
- **Draft or Revise Email**: Create or modify email content
- **Write a Sales Email**: Generate personalized sales emails
- **Draft a Case Response**: Prepare responses for customer cases
- **Log a Call**: Record call details and outcomes

#### Record Management
- **Summarize a Record**: Create summaries of record information
- **Summarize Record**: Generate record overviews
- **Create Case**: Generate new support cases
- **Get Activities Timeline**: Retrieve timeline of activities related to records

#### Routing & Escalation
- **Check Rep Availability for Routing**: Verify agent availability for escalation and routing
- **Transfer to Human Agent**: Handle handoff from AI agent to human representative

**Important Note:** There is NO standard Delete Record action in Agentforce. If deletion functionality is required, you must create a custom action using Flow or Apex.

### Custom Actions

There are three types of custom actions that extend Agentforce capabilities:

#### 1. Flow Actions
**Technology:** Salesforce Flows

**Use Cases:**
- Process automation
- User interactions
- Multi-step workflows
- Conditional logic implementation
- Integration with Salesforce automation

**Planning Considerations:**
- Map out the workflow steps
- Define input and output variables
- Identify decision points
- Consider error handling

#### 2. Apex Actions
**Technology:** Apex Code

**Use Cases:**
- Complex business logic
- External system integrations
- Advanced data manipulation
- Custom calculations
- API integrations

**Implementation:**
- Create Apex classes with invocable methods
- Handle exceptions appropriately
- Follow Apex best practices
- Consider governor limits

#### 3. Prompt Template Actions
**Technology:** Prompt Builder

**Use Cases:**
- Generate dynamic responses
- Trigger specific actions based on user input
- Create context-aware content
- Personalize interactions

**Types Available:**
- **Sales Email Prompt Template**: Personalized emails based on Salesforce data
- **Field Generation Prompt Template**: Generate field values (descriptions, summaries)
- **Record Summary Prompt Template**: Create record summaries from field values and related data
- **Flex Prompt Template**: Most flexible option for custom prompts using data from multiple objects

### Action Characteristics

- Actions cannot function without being linked to a topic
- Topics are ineffective without associated actions
- Actions can determine if user input is needed
- Actions can gather additional information during conversations
- Multiple actions can execute simultaneously

---

## Prompts and Templates

### Prompt Templates

Prompt templates are reusable AI prompts that generate dynamic content based on Salesforce data.

#### Types of Prompt Templates

1. **Sales Email Prompt Template**
   - Generate personalized, context-aware emails
   - Based on data stored in Salesforce
   - Customizable for different sales scenarios

2. **Field Generation Prompt Template**
   - Generate values for fields (descriptions, summaries, etc.)
   - Uses Salesforce data as context
   - Automates data entry tasks

3. **Record Summary Prompt Template**
   - Generate summaries of records
   - Based on field values and related data
   - Provides quick overviews of complex records

4. **Flex Prompt Template**
   - Most flexible template type
   - Select data from multiple Salesforce objects
   - Create custom prompts for unique use cases
   - User selection as input capability

### Invoking Prompts

Prompt templates can be invoked from:
- Salesforce Flows
- Apex code
- REST API
- Agentforce agents

---

## Best Practices

### Topic and Action Design

1. **Limit Actions per Topic**: Assign no more than 15 actions to a topic for best performance

2. **Clear Classification Descriptions**: Write precise classification descriptions so agents can accurately determine when to use each topic

3. **Well-Defined Scope**: Clearly define what an agent can and cannot do within each topic

4. **Meaningful Instructions**: Provide clear guidance to help agents make appropriate decisions

### Custom Action Development

1. **Planning Phase**:
   - Map out the complete workflow
   - Identify all required data sources
   - Define success criteria
   - Consider edge cases

2. **Security Considerations**:
   - Standard actions might be considered private actions
   - Review and configure security settings
   - Ensure compliance with organizational standards

3. **Testing**:
   - Test actions independently before integration
   - Validate error handling
   - Check performance under various conditions

### Agent Configuration

1. **Start with Standard Assets**: Use standard agents, topics, and actions as a foundation

2. **Customize Gradually**: Extend with custom actions only when standard options don't meet needs

3. **Monitor Performance**: Track agent effectiveness and adjust as needed

4. **User Feedback**: Collect and incorporate feedback from human users and customers

### Agentforce 2.0 Updates and Features

#### Coming February 2025
- **Enhanced Reasoning**: Generally available February 2025
- **Improved RAG (Retrieval-Augmented Generation)**: Generally available February 2025

#### Agentforce 2.0 Key Features

**Natural Language Agent Creation**
- Agent Builder uses Agentforce to compose new agents automatically
- Auto-generates relevant topics and instructions based on natural language descriptions
- Simplifies agent creation process for non-technical users

**Agent Versions**
- Create test versions of agents before deployment
- Verify that all new actions and topics work as intended
- Safe testing environment without affecting production agents
- Version control and rollback capabilities

**MuleSoft API Catalog Integration**
- View, discover, and manage APIs from one central location
- Access APIs across Salesforce, MuleSoft, Heroku, and external services
- Simplified integration with external systems
- Unified API management

**Pre-Built Agent Skills**
- Library of ready-to-use agent skills
- Skills available for:
  - CRM operations
  - Slack integrations
  - Tableau analytics
  - Partner-developed skills on AppExchange
- Accelerates agent deployment and customization

**New Standard Topics**
- Fallback Topic for handling unmatched queries
- Object Management Topic for admin operations
- Field Service Dispatcher Actions

---

## Use Case Examples

### Appointment Scheduling
- Schedule, reschedule, and cancel service appointments
- Optimize employee schedules
- Make, modify, or cancel reservations (dining, hotel, travel, events)
- Healthcare appointment management with check-ins and reminders
- Calendar synchronization and automated reminders

### Order Management
- Respond to order status queries
- Provide tracking details
- Inform customers of delivery times
- Report problems or delays
- Support order amendments (delivery schedule changes, modifications)
- Process order cancellations

### Case Resolution
- Resolve routine billing questions
- Perform general troubleshooting
- Handle appointment scheduling
- Transition inquiries to human representatives
- Direct conversations for sensitive assistance
- Identify and escalate customer dissatisfaction via sentiment analysis

### Sales Automation
- Autonomous lead outreach
- Product question responses
- Objection handling
- Meeting scheduling with qualified prospects
- Sales scenario role-playing and coaching

### Marketing Operations
- Campaign brief generation
- Audience segment creation
- Marketing content development
- Customer journey optimization

### Escalation and Agent-to-Human Handoff
- Seamless transfer of conversations from AI to human agents
- Context preservation during handoff
- Triggers include:
  - Complex or sensitive topics (billing disputes, cancellations)
  - Keyword detection ("talk to a person", "human agent")
  - Tone, intent, and emotion analysis
  - Customer dissatisfaction indicators
- Real-time context capture powered by NLP and machine learning
- Omni-Channel flow integration for routing to available agents
- Complexity threshold recognition for automatic escalation

---

## Architecture Overview

### Core Components

```
┌─────────────────────────────────────────────────────┐
│                   AGENTFORCE                         │
├─────────────────────────────────────────────────────┤
│                                                      │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐         │
│  │  AGENTS  │  │  TOPICS  │  │ ACTIONS  │         │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘         │
│       │             │              │                │
│       └─────────────┴──────────────┘                │
│                     │                               │
│            ┌────────┴────────┐                      │
│            │                 │                      │
│       ┌────▼─────┐     ┌────▼─────┐               │
│       │ Standard │     │  Custom  │               │
│       │  Assets  │     │  Assets  │               │
│       └──────────┘     └──────────┘               │
│                                                      │
├─────────────────────────────────────────────────────┤
│              EINSTEIN AI PLATFORM                    │
└─────────────────────────────────────────────────────┘
```

### Action Types

```
┌─────────────────────────────────────┐
│         CUSTOM ACTIONS              │
├─────────────────────────────────────┤
│                                     │
│  ┌────────────────────────────┐    │
│  │     Flow Actions           │    │
│  │  - Process Automation      │    │
│  │  - User Interactions       │    │
│  └────────────────────────────┘    │
│                                     │
│  ┌────────────────────────────┐    │
│  │     Apex Actions           │    │
│  │  - Complex Logic           │    │
│  │  - Integrations            │    │
│  └────────────────────────────┘    │
│                                     │
│  ┌────────────────────────────┐    │
│  │  Prompt Template Actions   │    │
│  │  - Dynamic Responses       │    │
│  │  - Content Generation      │    │
│  └────────────────────────────┘    │
│                                     │
└─────────────────────────────────────┘
```

---

## Summary

Agentforce represents a significant evolution in AI-powered business automation, moving from assistive AI (copilots) to autonomous AI agents that can independently handle complex business processes. The platform's modular architecture—combining agents, topics, and actions—provides flexibility while maintaining governance and control.

**Key Takeaways:**
- **7 Standard Agent Types** plus custom agent capabilities
- **30+ Standard Actions** including query, create, update, summarize, and routing capabilities
- **Standard Topics** for sales, service, commerce, marketing, and platform operations
- **Critical Topics**: Escalation for agent-to-human handoff, Fallback for unmatched queries, Object Management for admin tasks
- **Three Custom Action Types**: Flow, Apex, and Prompt Templates
- **No Delete Action**: Must create custom action for record deletion
- **Best Practice**: Maximum 15 actions per topic
- **Agentforce 2.0 Features**: Natural language agent creation, Agent Versions, MuleSoft API Catalog, pre-built skills
- **2025 Updates**: Enhanced reasoning and RAG capabilities coming in February

By leveraging Agentforce's comprehensive agent types, topics, and actions, organizations can scale their operations, improve customer experiences, and automate complex business processes with autonomous AI agents.

---

**Document Version:** 2.0
**Last Updated:** January 2025
**Sources:** Salesforce Official Documentation, Trailhead, Salesforce Community

**Version 2.0 Updates:**
- Added Escalation topic with agent-to-human handoff details
- Added Universal/Platform topics: Fallback and Object Management
- Added Field Service Dispatcher Actions topic
- Expanded standard actions list to 30+ with new categories for Routing & Escalation
- Added missing actions: Create Record, Update Record, Identify Object, Get Activities Timeline, Draft or Revise Email, Check Rep Availability for Routing
- Documented important limitation: No standard Delete Record action
- Expanded Agentforce 2.0 features: Natural language agent creation, Agent Versions, MuleSoft API Catalog, Pre-built agent skills
- Added dedicated section for Escalation and Agent-to-Human Handoff use cases

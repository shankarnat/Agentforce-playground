# Agentforce Overview: Topics, Actions, and Agent Types

## Table of Contents
- [What is Agentforce?](#what-is-agentforce)
- [Agent Types](#agent-types)
- [Topics](#topics)
- [Actions](#actions)
- [Instructions and How Agents Work](#instructions-and-how-agents-work)
- [Prompts and Templates](#prompts-and-templates)
- [Key Things to Know](#key-things-to-know)
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

## Instructions and How Agents Work

### The Agent Decision-Making Hierarchy

Agentforce agents operate using a sophisticated decision-making process powered by the **Atlas Reasoning Engine**, which acts as the "brain" of the system. Here's how the components work together:

```
┌─────────────────────────────────────────────────────┐
│                    USER INPUT                        │
│              "I need to return my order"             │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│         ATLAS REASONING ENGINE (Brain)               │
│                                                      │
│  1. Topic Classification: Matches input to topics   │
│  2. Planner: Creates step-by-step plan             │
│  3. Action Selector: Chooses appropriate actions   │
│  4. Executor: Runs the actions                      │
│  5. Observer: Validates results                     │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│              TOPIC SELECTED                          │
│           "Order Management"                         │
│                                                      │
│  ┌───────────────────────────────────────────┐      │
│  │  Classification Description               │      │
│  │  "Handles order-related requests"         │      │
│  └───────────────────────────────────────────┘      │
│                                                      │
│  ┌───────────────────────────────────────────┐      │
│  │  Scope                                     │      │
│  │  "Help customers with order tracking,     │      │
│  │   returns, and modifications"             │      │
│  └───────────────────────────────────────────┘      │
│                                                      │
│  ┌───────────────────────────────────────────┐      │
│  │  Instructions                              │      │
│  │  - Always ask for order number first      │      │
│  │  - Check return eligibility               │      │
│  │  - Use polite, professional tone          │      │
│  │  - Escalate if outside 30-day window      │      │
│  └───────────────────────────────────────────┘      │
│                                                      │
│  ┌───────────────────────────────────────────┐      │
│  │  Available Actions                         │      │
│  │  - Find Order                              │      │
│  │  - Track Order                             │      │
│  │  - Process Return                          │      │
│  │  - Generate Return Label                   │      │
│  └───────────────────────────────────────────┘      │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│         ACTIONS EXECUTED (Based on Instructions)     │
│                                                      │
│  1. "Find Order" action triggered                   │
│  2. Order retrieved from database                   │
│  3. "Process Return" action initiated               │
│  4. Return label generated                          │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│                  RESPONSE TO USER                    │
│  "I found your order #12345. Your return has been   │
│   approved. I've created a return label for you."   │
└─────────────────────────────────────────────────────┘
```

### The Four Key Components of a Topic

Every topic in Agentforce consists of four critical elements that work together:

#### 1. Classification Description
**Purpose:** Helps the agent determine if this topic should handle the current conversation

**How it works:** The Atlas Reasoning Engine compares the user's input to all topic names and classification descriptions to find the best match.

**Example:**
```
Topic: Order Management
Classification Description: "This topic handles all order-related requests including
order tracking, status inquiries, returns, exchanges, cancellations, and modifications."
```

**Best Practice:** Define broader classification descriptions to enable your agent to handle prompts outside your exact instructions that are still relevant to your topic.

#### 2. Scope
**Purpose:** Defines the agent's activities and boundaries within this topic

**How it works:** Establishes what the agent CAN and CANNOT do when this topic is active

**Example:**
```
Topic: Order Management
Scope: "Understand the customer's order number, order status, and desired action.
Using the order data available in Salesforce, help customers track orders,
process returns within the 30-day return window, and create return labels.
Your job is to make the return process seamless while ensuring company policy compliance."
```

**Best Practice:** Use commanding words like "Understand," "Using," "Your Job," "Help," and "Ensure" to make it clear what the agent should be doing at different stages.

#### 3. Instructions
**Purpose:** Provide detailed guidance on HOW the agent should behave and WHEN to trigger specific actions

**How it works:** Natural language instructions act as guardrails that guide the agent's decision-making, tone, and action selection

**Example:**
```
Topic: Order Management
Instructions:
- Always verify the customer's identity before discussing order details
- Ask for the order number if not provided in the initial request
- Check the order date to confirm return eligibility (must be within 30 days)
- Use a polite and empathetic tone, especially when delivering bad news
- If the order is outside the return window, explain the policy and escalate to a supervisor
- Format all dates as MM-DD-YYYY
- When processing a return, always:
  1. Confirm the reason for return
  2. Verify the items being returned
  3. Generate the return label
  4. Provide the return shipping address
  5. Set customer expectations for refund timeline (7-10 business days)
- If the customer seems frustrated (keywords: "angry," "disappointed," "unacceptable"),
  acknowledge their feelings and offer additional assistance
- Never promise refunds before confirming return eligibility
```

**Best Practice:** Write detailed instructions covering common cases, edge cases, tone requirements, formatting rules, and conditional logic for when to use specific actions.

#### 4. Example User Input (Optional)
**Purpose:** Provides sample utterances that should trigger this topic

**Example:**
```
Topic: Order Management
Example User Inputs:
- "Where is my order?"
- "I want to return my purchase"
- "Can I cancel my order?"
- "Track order #12345"
- "My package hasn't arrived yet"
```

### How Instructions Trigger Actions

Instructions use natural language to tell the agent **when** and **how** to use actions. Here's the relationship:

**Without Instructions (Actions alone):**
- Agent has tools but doesn't know when to use them
- May use actions inappropriately
- No context for decision-making

**With Instructions (Actions + Guidance):**
- Agent knows WHEN to trigger each action
- Understands the SEQUENCE of actions
- Applies business rules and guardrails

**Example - Pipeline Review Agent:**

```
Action: Generate Pipeline Summary
What it does: Retrieves pipeline metrics and generates a summary report

Instructions that trigger this action:
"When a sales rep asks for a pipeline overview or uses phrases like:
  - 'Show me my pipeline'
  - 'Pipeline review'
  - 'What deals do I have?'
  - 'Sales summary'

Execute the Generate Pipeline Summary action with these parameters:
  - Time period: Current quarter (unless specified otherwise)
  - Include metrics: Total deal value, number of deals, close probability, expected close dates
  - Group by: Deal stage
  - Sort by: Close date (ascending)

Present the results in a clear, formatted table with a brief narrative summary
highlighting the most important deals that need attention."

User utterances that trigger the action:
  - "Show me my pipeline"
  - "What's my sales forecast?"
  - "Review my deals"
```

### The ReAct Loop: Reasoning and Acting

Agentforce uses a **ReAct (Reasoning and Acting)** approach that cycles through these steps:

1. **Reason:** Analyze the user's request and current context
2. **Act:** Execute the appropriate action(s)
3. **Observe:** Validate the results
4. **Repeat:** Continue until the goal is fulfilled

**Example Conversation Flow:**

```
User: "I need to return my shoes from order 12345"

CYCLE 1:
├─ Reason: User wants to return items, need to find the order first
├─ Act: Execute "Find Order" action with order number 12345
├─ Observe: Order found, placed on 01-05-2025 (within return window)
└─ Continue: More steps needed

CYCLE 2:
├─ Reason: Order is eligible for return, need to process it
├─ Act: Execute "Process Return" action for order 12345
├─ Observe: Return approved, return ID generated
└─ Continue: Need to create shipping label

CYCLE 3:
├─ Reason: Return approved, customer needs return label
├─ Act: Execute "Generate Return Label" action
├─ Observe: Label created successfully
└─ Complete: User goal fulfilled

Agent Response: "Great news! I've processed your return for order #12345.
Your return has been approved. I've generated a return label that's been
emailed to you. Please ship the shoes back within 7 days. Your refund will
be processed within 7-10 business days after we receive the items."
```

### Guardrails and Instructions

**Guardrails** are a special type of instruction that define what agents CANNOT do. They protect your brand and ensure compliance.

**Types of Guardrails:**

1. **Behavioral Guardrails**
```
Instructions:
- Never make promises about refunds without confirming return eligibility
- Never share customer payment information
- Never process returns over $1,000 without manager approval
- Do not use casual language or emojis in professional contexts
```

2. **Tone Guardrails**
```
Instructions:
- Always use a professional, empathetic tone
- Avoid overly casual phrases like "no worries" or "awesome"
- When delivering bad news, acknowledge the customer's frustration before explaining policy
- Choose tone: Formal (for financial services), Neutral (for general business),
  Casual (for lifestyle brands)
```

3. **Security Guardrails**
```
Instructions:
- Never ask for full credit card numbers
- Always verify customer identity before discussing account details
- Escalate immediately if you detect potential fraud keywords:
  "test transaction," "verify card," "multiple shipping addresses"
```

4. **Compliance Guardrails**
```
Instructions:
- All refund timelines must state "7-10 business days" (company policy)
- Return window is strictly 30 days from purchase date
- International returns must go through special processing - use "International Return" action
- Certain items are non-returnable: hygiene products, customized items, opened software
```

### Conditional Filtering

**Conditional filters** work at the system level to include or exclude topics and actions based on specific conditions:

```
Example: Customer Tier-Based Topic Filtering

IF customer.tier == "Premium"
  THEN include topic: "Premium Support"
       include action: "Priority Escalation"
       include action: "Expedited Shipping"

ELSE IF customer.tier == "Standard"
  THEN exclude topic: "Premium Support"
       include action: "Standard Escalation"
```

**Benefits:**
- Reduces "semantic noise" during topic classification
- Improves accuracy of topic selection
- Personalizes the agent experience based on context

### Action Orchestration Example

**Scenario:** Customer wants to modify an order

```yaml
Topic: Order Management

Classification: "Handles order modifications, cancellations, and updates"

Scope: "Help customers modify orders that haven't shipped yet.
Your job is to check order status, determine if modification is possible,
and process changes while keeping customers informed."

Instructions: |
  When a customer wants to modify an order, follow this sequence:

  Step 1: Information Gathering
    - Ask for order number if not provided
    - Ask what specific change they want to make

  Step 2: Verification (use "Find Order" action)
    - Retrieve the order details
    - Check the order status

  Step 3: Decision Logic
    IF order.status == "Processing" OR order.status == "Pending"
      THEN modifications are allowed
      PROCEED to Step 4
    ELSE IF order.status == "Shipped"
      THEN modifications NOT allowed
      EXPLAIN that order has shipped, offer return process instead
      TRIGGER "Escalation" topic if customer is frustrated
      STOP

  Step 4: Process Modification (use appropriate actions)
    IF modification_type == "address change"
      THEN use "Update Shipping Address" action
    ELSE IF modification_type == "item change"
      THEN use "Modify Order Items" action
    ELSE IF modification_type == "cancel"
      THEN use "Cancel Order" action

  Step 5: Confirmation
    - Use "Send Order Confirmation Email" action
    - Inform customer of the change
    - Provide updated order details
    - Set expectations for new delivery timeline if applicable

  Tone: Professional and helpful
  Format dates: MM-DD-YYYY
  Always confirm changes with the customer before executing

Actions:
  - Find Order
  - Update Shipping Address
  - Modify Order Items
  - Cancel Order
  - Send Order Confirmation Email
  - Escalate to Human Agent

Example User Inputs:
  - "I need to change my shipping address"
  - "Can I cancel order 12345?"
  - "I want to add another item to my order"
  - "Change delivery address for my order"
```

### Summary: How It All Works Together

1. **User sends a message** → Atlas Reasoning Engine receives input

2. **Topic Classification** → Engine compares message to all topic classification descriptions and selects the best match

3. **Topic Activated** → Scope and instructions for that topic become active

4. **Instructions Guide Actions** → Natural language instructions tell the agent when and how to use available actions

5. **Actions Execute** → Agent performs specific tasks (query data, create records, send emails)

6. **Guardrails Enforced** → Agent follows boundaries defined in instructions

7. **ReAct Loop** → Agent reasons, acts, observes, and repeats until goal is achieved

8. **Response Generated** → Agent provides answer following tone and formatting instructions

The key insight: **Instructions are the bridge between user intent and action execution. They provide the business logic, context, and guardrails that transform a collection of actions into intelligent, purposeful agent behavior.**

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

## Key Things to Know

### Critical Concepts for Agents, Topics, and Actions

#### 1. **Hierarchical Relationship**
```
AGENT
 ├── Topic 1
 │    ├── Classification Description
 │    ├── Scope
 │    ├── Instructions
 │    └── Actions (1-15 recommended)
 │         ├── Action A
 │         ├── Action B
 │         └── Action C
 ├── Topic 2
 │    └── ...
 └── Topic 3
      └── ...
```

**Key Points:**
- An **Agent** can have multiple **Topics**
- Each **Topic** must have Classification Description, Scope, and Instructions
- Each **Topic** contains 1-15 **Actions** (max 15 for best performance)
- **Actions cannot exist without a Topic**
- **Topics are ineffective without Actions**

#### 2. **The Atlas Reasoning Engine**

**What it is:** The "brain" of Agentforce that powers decision-making

**What it does:**
- **Topic Classification:** Matches user input to the right topic
- **Planning:** Creates step-by-step plans to achieve user goals
- **Action Selection:** Chooses which actions to execute
- **Execution:** Runs the selected actions
- **Observation:** Validates results and adjusts as needed

**How it works:** Uses ReAct (Reasoning and Acting) methodology in a continuous loop until the user's goal is fulfilled

**Important:** The reasoning process is transparent and auditable, allowing admins to see WHY the agent made specific decisions

#### 3. **Instructions Are Everything**

**Without good instructions:**
- Agents don't know when to use actions
- No business logic or context
- Inconsistent behavior
- Poor user experience

**With good instructions:**
- Clear action triggering rules
- Consistent tone and behavior
- Business rule enforcement
- Guardrails and compliance

**Best Practice:** Write instructions in one large, cohesive block rather than fragments. Include:
- When to trigger specific actions
- How to sequence actions
- What tone to use
- Edge case handling
- Format requirements (dates, numbers, etc.)
- Escalation criteria

#### 4. **Standard vs Custom Assets**

| Asset Type | Standard | Custom |
|------------|----------|--------|
| **Agent Types** | 7 pre-built (SDR, Service, Coach, etc.) | Unlimited via Agent Builder |
| **Topics** | Library of standard topics (Case Mgmt, Orders, Escalation, etc.) | Create unlimited custom topics |
| **Actions** | ~30 out-of-the-box actions | Flow, Apex, or Prompt Template actions |
| **Setup Time** | Minutes | Hours to days |
| **Customization** | Limited | Fully customizable |
| **Maintenance** | Salesforce managed | You manage |

**Strategy:** Start with standard assets, then extend with custom topics and actions as needed

#### 5. **Topic Limits and Best Practices**

| Aspect | Limit/Recommendation | Why |
|--------|---------------------|-----|
| Actions per Topic | Max 15 | Performance optimization, reduces decision complexity |
| Topics per Agent | No hard limit | Too many topics = harder classification, slower performance |
| Classification Description | Be specific but not too narrow | Too narrow = missed matches; Too broad = wrong topic selected |
| Instructions Length | Detailed is better | More context = better decisions, but stay focused on the topic |

#### 6. **The Four Components Framework**

Every topic MUST have these four elements properly configured:

1. **Classification Description** → Answers: "When should this topic be used?"
2. **Scope** → Answers: "What can the agent do/not do in this topic?"
3. **Instructions** → Answers: "How should the agent behave and use actions?"
4. **Actions** → Answers: "What tools are available to complete the job?"

**Missing any of these = Topic won't work properly**

#### 7. **Action Limitations to Remember**

**What EXISTS:**
- Query Records ✅
- Create Record ✅
- Update Record ✅
- Summarize Record ✅
- Get Record Details ✅

**What DOESN'T EXIST:**
- ❌ Delete Record (NO standard delete action)
- ❌ Bulk operations (must create custom actions)
- ❌ Complex calculations (must create custom Apex actions)

**Solution:** Use custom Flow or Apex actions for missing functionality

#### 8. **Guardrails Are Non-Negotiable**

**Why Guardrails Matter:**
- Prevent AI hallucinations
- Protect brand reputation
- Ensure compliance with regulations
- Prevent security breaches
- Maintain consistent customer experience

**Types You Need:**
1. **Security:** Never share PII, verify identity, detect fraud
2. **Compliance:** Follow company policies, regulatory requirements
3. **Behavioral:** Don't make unauthorized promises, escalate when needed
4. **Tone:** Maintain brand voice, appropriate language

**Implementation:** Write guardrails as negative instructions:
```
- Never [prohibited action]
- Do not [unwanted behavior]
- Always escalate if [condition]
- Avoid [undesired language/tone]
```

#### 9. **Topic Selection Mechanics**

**How the engine selects topics:**

```
User Input: "I want to return my shoes"

Step 1: Compare to all topic names
  - "Order Management" (partial match)
  - "Account Support" (no match)
  - "Product Catalog" (no match)

Step 2: Compare to classification descriptions
  - "Order Management": "Handles orders, returns, tracking..." (STRONG MATCH ✅)
  - "Account Support": "Manages account settings..." (weak match)
  - "Product Catalog": "Provides product info..." (weak match)

Step 3: Apply conditional filters (if any)
  - Check if user qualifies for topic based on conditions
  - Remove filtered-out topics

Step 4: Select best match
  - Winner: "Order Management" topic
  - Load its scope, instructions, and actions
```

**Pro Tip:** Use similar keywords in your classification description as users would naturally use

#### 10. **Action Orchestration Flow**

Actions don't just run randomly. Instructions define the **sequence**:

```
Example: Return Processing Flow

Instruction-Defined Sequence:
1. First → "Find Order" action (must happen before anything else)
2. Then → Check eligibility (conditional logic in instructions)
3. If eligible → "Process Return" action
4. Then → "Generate Return Label" action
5. Finally → "Send Confirmation Email" action

If any step fails → Instructions define fallback behavior
```

**Key Insight:** Instructions create the workflow. Actions are just tools.

#### 11. **Tone and Brand Consistency**

**Tone Options:**
- **Formal:** Financial services, legal, enterprise B2B
- **Neutral:** General business, SaaS, B2B
- **Casual:** Consumer brands, lifestyle, B2C

**Consistency Requirements:**
- Define tone in agent-level instructions AND topic-level instructions
- Use tone guardrails to prevent deviations
- Test with edge cases to ensure tone remains consistent

**Example:**
```
Formal: "We regret to inform you that your order is outside the return window."
Neutral: "Your order was placed 45 days ago, which is outside our 30-day return policy."
Casual: "Unfortunately, it's been over 30 days since you ordered, so we can't process a return."
```

#### 12. **Escalation Rules**

**When agents should escalate to humans:**

1. **Complexity Threshold:** Agent can't resolve with available actions
2. **Sentiment Detection:** Customer frustration detected
3. **Policy Exceptions:** Request outside standard guidelines
4. **High-Value Transactions:** Above a certain $ amount
5. **Explicit Request:** Customer asks for human agent

**How to implement:**
- Add "Escalation" standard topic to your agent
- Define escalation triggers in instructions
- Configure Omni-Channel flow for routing
- Use "Check Rep Availability for Routing" action

#### 13. **Testing and Validation**

**What to test:**

✅ Topic classification accuracy
- Does the right topic activate for different user inputs?

✅ Action triggering
- Do actions execute at the right time?
- Are action sequences correct?

✅ Guardrails enforcement
- Does the agent refuse prohibited actions?
- Is tone consistent?

✅ Edge cases
- What happens when data is missing?
- How does it handle unexpected inputs?

✅ Escalation paths
- Does escalation trigger appropriately?
- Is context preserved during handoff?

**Use Agent Versions (Agentforce 2.0)** to test safely before deploying to production

#### 14. **Common Pitfalls to Avoid**

| Pitfall | Problem | Solution |
|---------|---------|----------|
| Too many actions per topic | Confuses the agent, slow performance | Keep to 15 or fewer per topic |
| Vague instructions | Inconsistent agent behavior | Be specific, detailed, and comprehensive |
| Missing guardrails | Agent makes mistakes, brand risk | Define clear boundaries and limitations |
| Overlapping topics | Wrong topic selected | Make classification descriptions distinct |
| No escalation path | Agent gets stuck on complex issues | Always include Escalation topic |
| Ignoring tone | Inconsistent brand voice | Define and enforce tone requirements |
| Not testing edge cases | Failures in production | Test thoroughly with Agent Versions |

#### 15. **The Agentforce Success Formula**

```
Successful Agent =
  Clear Agent Purpose
  + Well-Defined Topics (with all 4 components)
  + Appropriate Actions (standard + custom)
  + Detailed Instructions (including guardrails)
  + Proper Testing (using Agent Versions)
  + Continuous Monitoring and Refinement
```

**Remember:**
1. Start simple → Deploy one topic with a few actions
2. Test thoroughly → Use different phrasings and edge cases
3. Monitor performance → Track topic classification accuracy and action success rates
4. Iterate → Refine instructions based on real usage
5. Expand gradually → Add topics and actions as you validate success

#### 16. **Data and Context Access**

**What agents can access:**
- Salesforce records (based on permissions)
- Knowledge articles
- External data via MuleSoft API Catalog (Agentforce 2.0)
- Custom data via Flow and Apex actions

**What agents CANNOT access:**
- Data outside their security permissions
- Deleted or archived records (without custom actions)
- External systems without proper integration

**Best Practice:** Use conditional filtering to show/hide topics based on user permissions or data availability

#### 17. **Natural Language Processing Capabilities**

**What agents understand:**
- Intent: "I want to..." "Can you..." "Help me..."
- Context: References to previous messages in the conversation
- Entities: Order numbers, dates, names, product IDs
- Sentiment: Frustration, satisfaction, urgency
- Variations: Different ways of saying the same thing

**What helps agents understand better:**
- Example user inputs in topic configuration
- Detailed classification descriptions
- Keywords in instructions
- Consistent terminology across topics

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
- **Atlas Reasoning Engine**: Powers decision-making using ReAct (Reasoning and Acting) methodology
- **Four Topic Components**: Classification Description, Scope, Instructions, Actions (all required)
- **Instructions Are Key**: Bridge between user intent and action execution; provide business logic, context, and guardrails
- **Guardrails**: Essential for security, compliance, behavioral boundaries, and tone consistency
- **Agentforce 2.0 Features**: Natural language agent creation, Agent Versions, MuleSoft API Catalog, pre-built skills
- **2025 Updates**: Enhanced reasoning and RAG capabilities coming in February

By leveraging Agentforce's comprehensive agent types, topics, and actions, organizations can scale their operations, improve customer experiences, and automate complex business processes with autonomous AI agents.

---

**Document Version:** 3.0
**Last Updated:** January 2025
**Sources:** Salesforce Official Documentation, Trailhead, Salesforce Community

**Version 3.0 Updates (Latest):**
- **NEW: Instructions and How Agents Work section** - Comprehensive explanation of how instructions trigger actions and topics
  - Added Agent Decision-Making Hierarchy with visual flow diagram
  - Explained the four key components of a topic (Classification, Scope, Instructions, Example Inputs)
  - Detailed how instructions trigger actions with real examples
  - Documented the ReAct (Reasoning and Acting) loop with example conversation flow
  - Added Guardrails types and examples (Behavioral, Tone, Security, Compliance)
  - Explained Conditional Filtering with examples
  - Provided complete Action Orchestration example (Order Management scenario)
- **NEW: Key Things to Know section** - 17 critical concepts covering:
  - Hierarchical relationship between agents, topics, and actions
  - Atlas Reasoning Engine deep dive
  - Instructions best practices
  - Standard vs Custom assets comparison
  - Topic limits and recommendations
  - Four Components Framework
  - Action limitations (what exists vs what doesn't)
  - Guardrails implementation
  - Topic selection mechanics
  - Action orchestration flow
  - Tone and brand consistency
  - Escalation rules
  - Testing and validation checklist
  - Common pitfalls to avoid
  - Agentforce success formula
  - Data and context access
  - Natural language processing capabilities

**Version 2.0 Updates:**
- Added Escalation topic with agent-to-human handoff details
- Added Universal/Platform topics: Fallback and Object Management
- Added Field Service Dispatcher Actions topic
- Expanded standard actions list to 30+ with new categories for Routing & Escalation
- Added missing actions: Create Record, Update Record, Identify Object, Get Activities Timeline, Draft or Revise Email, Check Rep Availability for Routing
- Documented important limitation: No standard Delete Record action
- Expanded Agentforce 2.0 features: Natural language agent creation, Agent Versions, MuleSoft API Catalog, Pre-built agent skills
- Added dedicated section for Escalation and Agent-to-Human Handoff use cases

**Version 1.0 (Initial Release):**
- Documented 7 standard agent types
- Listed standard topics for Service, Sales, Commerce, and Marketing
- Catalogued standard actions
- Explained custom action types (Flow, Apex, Prompt Templates)
- Provided use case examples

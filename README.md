# AI-Ticket-Routing-Tool

An internal AI-powered tool that automatically classifies incoming tickets and suggestions based on whether they require a product-level decision, and routes them to the appropriate owner.

## Problem

Incoming tickets and suggestions traditionally need to be manually read, interpreted, and assigned to the relevant team. This creates a manual bottleneck, consumes time, and introduces inconsistency in how requests are routed.

The goal of this MVP is to automate the initial classification and routing step while keeping the routing logic explainable.

## How It Works

The tool follows a two-stage process:

1. **Ticket Submission**
   - User enters the ticket **Title, Description, and Submitter**.

2. **AI Analysis**
   - The AI analyzes the ticket context and determines whether it requires a **product-level decision**.

3. **Decision Classification**
   - **Decision Required →** routed to the Product Manager.
   - **No Decision Required →** classified into an execution category such as Design, Development, or QA.

4. **Deterministic Routing**
   - Predefined routing rules assign the ticket to the relevant execution team.
   - The tool also provides a reason for the routing decision.

5. **Result & History**
   - The classification, assigned owner/team, and routing result are displayed and stored in the ticket history.

### Example

**Ticket:**  
"Add Dark Mode option in website"

**Result:**  
Decision Required → Product Manager

Whereas:

**Ticket:**  
"Checkout button not working"

**Result:**  
No Decision Required → Development Team

The key principle is that a UI or design change does **not** automatically mean a PM decision is required. The system looks for actual product-level judgment, prioritization, trade-offs, approval, or clarification.

## Assumptions 

The MVP intentionally focuses on the core classification and routing workflow.

- **AI + rule-based hybrid:** AI is used to understand and classify the ticket, while deterministic rules control the final routing.
- **Predefined teams:** The MVP uses a limited set of execution categories such as Design, Development, and QA rather than dynamically discovering teams.
- **PM as the decision owner:** Any ticket classified as requiring a product-level decision is routed to the Product Manager.
- **Ambiguous requests:** Requests that cannot be confidently routed are intended to be handled through a manual-review/fallback path rather than being randomly assigned.

## MVP Scope

- Ticket submission
- AI-powered ticket analysis
- Decision Required / No Decision Required classification
- Request category classification
- Automatic routing
- Explainable routing reason
- Ticket/result history

## Live MVP

[View the Live MVP](https://ai-ticket-routing-tool.lovable.app/)


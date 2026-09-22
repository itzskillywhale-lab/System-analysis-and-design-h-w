# User Story: Place an Order

## User Story

**As a** customer,  
**I want to** place an order for the items in my shopping cart,  
**so that** I can purchase the items and have them delivered to my address.

## Acceptance Criteria

### Scenario: Customer successfully places an order

**Given** a customer has items in their shopping cart  
**And** the customer has entered a valid delivery address  
**When** the customer completes the payment successfully  
**Then** the system should create the order  
**And** reduce the available stock for the purchased items  
**And** display an order confirmation message to the customer  
**And** send an order confirmation notification to the customer.

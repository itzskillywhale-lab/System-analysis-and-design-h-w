# Context Diagram: Online Shopping System

```mermaid
flowchart LR
    Customer -->|Places order / Makes payment| OnlineStore
    OnlineStore -->|Order confirmation| Customer

    OnlineStore -->|Payment request| PaymentGateway
    PaymentGateway -->|Payment confirmation| OnlineStore

    OnlineStore -->|Update stock| InventorySystem
    InventorySystem -->|Stock information| OnlineStore

    OnlineStore -->|Send notification| NotificationService
    NotificationService -->|Order confirmation| Customer
```

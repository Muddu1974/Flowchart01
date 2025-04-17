```mermaid
graph TD
    A[Create Sales Order] --> B{MRP Run for Sales Order};
    B -- Yes --> C[Generate Production Demands (Based on BOM & Routing)];
    C --> D[Convert Production Demands to Production Orders (3 Orders)];
    D --> E{Production Order Steps (10-50)};
    E -- Completed for all 3 Orders --> F[Decision: Combine Remaining Steps?];
    F -- Yes --> G[Create New Production Order (Combining 3 Previous Orders)];
    G --> H{New Production Order Steps (60-80)};
    H --> I[Production Completed (Combined Order)];
    F -- No --> J[Continue Individual Production Orders (Steps 60-80)];
    J --> K[Production Completed (Individual Orders)];
```

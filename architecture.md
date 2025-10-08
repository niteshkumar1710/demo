graph TD
    subgraph Frontend
        A[1. Simulation Editor (Client/UI)]
    end
    subgraph Backend Services
        B[2. Collaboration & Sync Service]
        C[3. Model & Version Control Service]
        D[4. Project Management Service]
        E[5. Issue & Feedback Service]
    end

    A -->|User Actions/Edits| B
    B -- Real-time Sync --> A
    B -->|Save Snapshot| C
    A -->|Load Model| C
    A -->|View/Create Issues & Comments| E
    E -->|Notify Tagged User| D
    C -->|Auth Check| D
    A -->|Login/Role Check| D

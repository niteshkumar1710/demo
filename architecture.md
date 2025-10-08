graph LR
    C_MVC[3. Model & Version Control Service]
    D_PM[4. Project Management Service]
    B_COLLAB[2. Collaboration & Sync Service]
    E_FEEDBACK[5. Issue & Feedback Service]

    %% Dependencies on Project Management for Auth/Status
    C_MVC -->|1. Check Permissions (Edit/Branch)| D_PM
    B_COLLAB -->|2. Check Session Status (Freeze/In Progress)| D_PM
    
    %% Data Flow
    B_COLLAB -->|3. Save Finalized Edits (Snapshot)| C_MVC
    E_FEEDBACK -->|4. Get Model Context (\#Node)| C_MVC
    
    %% Notifications
    D_PM -->|5. Notify Members (Status Change)| E_FEEDBACK
    E_FEEDBACK -->|6. Notify User (@Tagging)| D_PM

graph TD
    Start((Start)) --> Assess_Risks{Assess Risks?}
    Assess_Risks --> |No| End((End))
    Assess_Risks --> |Yes| Implement_Changes{Implement Changes}
    Implement_Changes --> Review_Changes{Review Changes}
    Review_Changes --> |Approved| Deploy_Changes((Deploy Changes))
    Review_Changes --> |Rejected| Implement_Changes
    Deploy_Changes --> |Success| End
    Deploy_Changes --> |Failed| Implement_Changes

    subgraph Assess_Risks
        Check_Staging_Libraries[Check Staging Libraries]
        Create_Change_Ticket[Create Change Ticket]
        Obtain_Password[Obtain Password]
        Make_Changes[Make Changes]
        Move_to_Staging_Library[Move to Staging Library]
        Check_Staging_Libraries --> Create_Change_Ticket
        Create_Change_Ticket --> Obtain_Password
        Obtain_Password --> Make_Changes
        Make_Changes --> Move_to_Staging_Library
    end

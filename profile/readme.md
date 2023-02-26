# Project Overview

## components
- Web Interface
- REST API
- Package metric CLI

```mermaid
graph LR
    subgraph ACME
    client1
    client2
    client3
    client4
    client5
    end
    subgraph "Google Cloud Platform"
    Web_Interface -- authenticated request <--> REST_API
    REST_API <--> Trustworthy_module_cli 
    REST_API <--> Database
    end
    subgraph "Github"
    GitHubAPI
    end
    client1 --> Web_Interface
    client2 --> Web_Interface
    client3 --> Web_Interface
    client4 --> Web_Interface
    client5 --> Web_Interface
    Trustworthy_module_cli <--> GitHubAPI
```

## Data flow & Security

```mermaid
graph LR
    subgraph ACME
    Admin
    User
    end
    
    subgraph "Google Cloud Platform"
    subgraph Web_Interface
    Login
    Package_registry_frontend
    end
    
    Web_Interface -- authenticated request <--> REST_API
    REST_API
    end

    ACME -- credentials <--> Login
    Admin -- Register Users --> Web_Interface

    Admin -- Upload/Download/Search <--> Web_Interface
    User -- Upload/Download/Search <--> Web_Interface

```

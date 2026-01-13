# Day-13 – Need of Client-Server Architecture – Core Model

## Why Client-Server was Needed
- Shared data became unavoidable → file/standalone systems caused corruption
- Users were no longer in the same room → unreliable networks
- Scaling users ≠ scaling machines → vertical scaling failed
- Logic duplication on clients → inconsistency and bugs

## Key Insight
- Centralize **data + rules**
- Distribute **interaction (UI)**
- Ship **requests**, not raw data
- Verify **centrally**, don’t trust clients

## What is Client-Server Model
- **Client**: Initiates requests, handles UI and user interaction
- **Server**: Validates requests, executes business logic, manages shared resources
- Flow: Client asks → Server decides

## Interaction Flow
1. Client sends request
2. Server authenticates & authorizes
3. Server executes business logic
4. Server interacts with DB/cache/services
5. Server returns response

## Why This Model Scales
- Single source of truth
- Centralized control, distributed access
- Loose coupling (clients and servers evolve independently)

## What Client-Server Is NOT
- Not just frontend-backend
- Not automatically scalable
- Not automatically secure
- Not always two machines

## Core Rule
> Trust lives on the server.  
> Interaction lives on the client.
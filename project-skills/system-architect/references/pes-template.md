# PES Template (Product Engineering Spec)

## Feature Name
[Name — must match the PRD]

## Architecture Overview
```mermaid
graph TD
    A[Client] --> B[API Gateway]
    B --> C[Service A]
    B --> D[Service B]
    C --> E[(Database)]
    D --> F[(Cache)]
```

## Component Design

### [Component Name]
- **Responsibility:** [single responsibility description]
- **Technology:** [chosen technology]
- **Rationale:** [why this technology over alternatives]
- **Interfaces:** [API contracts this component exposes]

## Data Flow
```mermaid
sequenceDiagram
    participant U as User
    participant A as API
    participant S as Service
    participant D as Database
    U->>A: Request
    A->>S: Process
    S->>D: Query
    D-->>S: Result
    S-->>A: Response
    A-->>U: Result
```

## API Contract (OpenAPI)
```yaml
paths:
  /api/v1/resource:
    post:
      summary: [description]
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                field: { type: string }
      responses:
        '200':
          description: Success
        '400':
          description: Validation error
```

## Database Schema
[ERD or table definitions]

## Architecture Decision Records

| Decision | Options Considered | Chosen | Rationale | Revisit When |
|----------|-------------------|--------|-----------|--------------|
| [topic]  | [A, B, C]         | [B]    | [why]     | [condition]  |

## Security Considerations
- **Authentication:** [method]
- **Authorization:** [model]
- **Data encryption:** [at rest, in transit]

## Technical Risks
| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| [risk] | [H/M/L]  | [H/M/L] | [strategy] |

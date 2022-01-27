# example mermaid

![](https://img.shields.io/badge/mermaid-8.13.10-lightgreen)

This is just a demo web application using "Mermaid". It lets you create diagrams and visualizations using text and code.

See demo: https://lightzane.github.io/example-mermaid

### Graph

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

### Flowchart

```mermaid
flowchart TD
    A[Start] --> B{Is it?};
    B -->|Yes| C[OK];
    C --> D[Rethink];
    D --> B;
    B ---->|No| E[End];
```

`TD` = Top Down
`LR` = Left Right

### Sequence Diagram

```mermaid
sequenceDiagram
    participant Nat
    participant Ivy
    Nat->>John: Hello John, how are you?
    loop Lifecheck
        John->>John: Fight against sad life
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Nat: Great!
    John->>Ivy: How about you?
    Ivy-->>John: Jolly good!
```

### Gantt Chart

```mermaid
gantt
    dateFormat  MM-DD-YYYY
    title My very good Gantt chart

    section Todo
    Watch Netflix     :done,    01-21-2022, 5d
    Play games        :active,        01-25-2022, 2d
    Play more games   : ,  01-27-2022, 5d
```

### Sequence Diagram (extended)

```mermaid
sequenceDiagram
    actor A as You
    participant B as ATM
    participant C as Bank Server
    participant D as Bank Account

    A ->>   +B: Insert Card
    B ->>   +C: Verify Card

    alt happy path
    C -->>  B: Card OK!
    B ->>   A: Request PIN

    else sad path
    C -->>-  B: Card Invalid
    Note right of A: Hmm, Is there a human behind this ATM?
    B -)-  A: Eject Card
    end

    A -->>  +B: PIN Entered
    B ->>   +C: Verify PIN

    alt happy path
    C -->>  B: PIN OK
    B ->>   A: Request Amount

    else sad path
    C -->>  B: PIN Invalid
    B -)-   A: Eject Card
    end

    A -->>  +B: Amount entered
    B ->>   C: Start Transaction
    C ->>   +D: Sufficient funds ?

    alt if funds are sufficient
    D -->>  C: Funds OK
    C ->>   D: Withdraw Amount
    D -->>  C: Withdraw Successful
    C -->>  B: Transaction Successful
    B ->>   A: Dispense Cash

    else sad no money
    D -->>  -C: Insufficient Funds
    C -->>-  B: Transaction Unsuccessful
    end

    B -)-   A: Eject Card
```

# Reference

-   https://mermaid-js.github.io/mermaid/#/
-   https://unpkg.com/mermaid@8.13.10/dist/mermaid.core.js

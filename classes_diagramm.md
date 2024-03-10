<!-- 
uml code
@startuml classes
package TicketSystem {
    
    class Ticket {
        - match: Match
        - seat: Seat
        + Ticket(match: Match, seat: Seat)
        + getMatch(): Match
        + getSeat(): Seat
    }

    class Match {
        - date: Date
        - teams: String[]
        + Match(date: Date, teams: String[])
        + getDate(): Date
        + getTeams(): String[]
    }

    class Stadium {
        - name: String
        - location: String
        - capacity: int
        + Stadium(name: String, location: String, capacity: int)
        + getName(): String
        + getLocation(): String
        + getCapacity(): int
    }

    class Seat {
        - number: int
        - row: int
        + Seat(number: int, row: int)
        + getNumber(): int
        + getRow(): int
    }
}

package TicketSales {
    class TicketOffice {
        - tickets: List<Ticket>
        + TicketOffice()
        + sellTicket(ticket: Ticket): void
        + refundTicket(ticket: Ticket): void
    }

    class TicketSeller {
        + TicketSeller()
    }

    class TicketManager {
        - ticketScanner: TicketScanner
        + TicketManager(scanner: TicketScanner)
        + scanTicket(ticket: Ticket): void
    }

    class PaymentGateway {
        + PaymentGateway()
    }
}

package AccessControl {
    class TicketScanner {
        + TicketScanner()
        + scanTicket(ticket: Ticket): void
    }
}

Ticket -- Match
Ticket *-- Stadium
Ticket *-- Seat
TicketOffice "1"-- "*" Ticket
TicketOffice o-- TicketSeller
TicketOffice o-- TicketManager
TicketManager -- TicketScanner
PaymentGateway <|-- TicketOffice
@enduml 
-->


<!-- for decode uml - //www.plantuml.com/plantuml/png/bLNDRjD04BxxALOvkQrpu6fLgAX8N5f0f3V4OLXFmghsBjgT44N0kpDs1ZBZ15NnmPM_dvblThhjNI78j1twwZluPzYWUmh-6McrBuI3-ravVdmFfGWnGl8itG3alxNkSVoXu890hLln-nzu8_PQMngbl5BI3TB4rrSYjDmeP-hOu7UbOau6ax83mjQzvRS22M4eN8DoY9lFNrI7G-kZgPbhPr573SUPj9Pv6drCcIucBJFGXUrWyaOOyAz7mNtoG275CvG7tbwWVUj2r6SkrMjTiJafr5Z_RBptx3tEOBa7gVG__bxgCY_9vkCZa9rzEtp5FAaLcjFkP3HsrahTYEWq_wIH19Rwb7Os6MURNGFeiPov1H_Mw-3H9AU9AArx28Lk3xBNgfysrZfZmRwNot6eqOgMe_r8eLFIZEjjx5uKcoEMGRW9PXNunX0Iw8pn4I9in6b7NNc84JC7q9-gWIbGbxDoSn0CNJRRHzWF6EaT4EvWRwQpbCndDlp6UopbFaNAgJSxDWbDLSFK5uQN_WVOBPVojqs-hncG-seW1AhCBztYrOBnnVL26bWsCQStUygQjLHsoqpRRSvE-FONAtJ5wWvZD_xx-0C0 -->

<img src="https://www.plantuml.com/plantuml/svg/bLNDRjD04BxxALOvkQrpu6fLgAX8N5f0f3V4OLXFmghsBjgT44N0kpDs1ZBZ15NnmPM_dvblThhjNI78j1twwZluPzYWUmh-6McrBuI3-ravVdmFfGWnGl8itG3alxNkSVoXu890hLln-nzu8_PQMngbl5BI3TB4rrSYjDmeP-hOu7UbOau6ax83mjQzvRS22M4eN8DoY9lFNrI7G-kZgPbhPr573SUPj9Pv6drCcIucBJFGXUrWyaOOyAz7mNtoG275CvG7tbwWVUj2r6SkrMjTiJafr5Z_RBptx3tEOBa7gVG__bxgCY_9vkCZa9rzEtp5FAaLcjFkP3HsrahTYEWq_wIH19Rwb7Os6MURNGFeiPov1H_Mw-3H9AU9AArx28Lk3xBNgfysrZfZmRwNot6eqOgMe_r8eLFIZEjjx5uKcoEMGRW9PXNunX0Iw8pn4I9in6b7NNc84JC7q9-gWIbGbxDoSn0CNJRRHzWF6EaT4EvWRwQpbCndDlp6UopbFaNAgJSxDWbDLSFK5uQN_WVOBPVojqs-hncG-seW1AhCBztYrOBnnVL26bWsCQStUygQjLHsoqpRRSvE-FONAtJ5wWvZD_xx-0C0" alt="Golang Version">



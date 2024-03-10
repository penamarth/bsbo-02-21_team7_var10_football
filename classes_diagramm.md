```
@startuml
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
        - stadium: Stadium
        + Match(date: Date, teams: String[], stadium: Stadium)
        + getDate(): Date
        + getTeams(): String[]
        + getStadium(): Stadium
        + setStadium(stadium: Stadium): void
    }

    class Stadium {
        - name: String
        - location: String
        - capacity: int
        + Stadium(name: String, location: String, capacity: int)
        + getName(): String
        + setName(name: String): void
        + getLocation(): String
        + setLocation(location: String): void
        + getCapacity(): int
        + setCapacity(capacity: int): void
    }

    class Seat {
        - number: int
        - row: int
        + Seat(number: int, row: int)
        + getNumber(): int
        + setNumber(number: int): void
        + getRow(): int
        + setRow(row: int): void
    }
}

package TicketSales {
    class TicketOffice {
        - tickets: List<Ticket>
        - ticketManager: TicketManager
        + TicketOffice()
        + sellTicket(ticket: Ticket): void
        + refundTicket(ticket: Ticket): void
    }

    class TicketSeller {
        - name: String
        - employeeID: String
        + TicketSeller(name: String, employeeID: String)
        + greetCustomer(): void
        + provideInformation(): void
    }

    class TicketManager {
        - ticketScanner: TicketScanner
        + TicketManager(scanner: TicketScanner)
        + scanTicket(ticket: Ticket): bool
    }

    class PaymentGateway {
        + PaymentGateway()
        + processPayment(amount: double): boolean
        + getPaymentStatus(paymentID: String): String
    }
}


package AccessControl {
    class TicketScanner {
        + TicketScanner()
        + scanTicket(ticket: Ticket): bool
    }
}

interface ITicketScan {
    + TicketScanner()
    + scanTicket(ticket: Ticket): bool
}


Ticket -- Match
Match *-- Stadium
Ticket *-- Seat
TicketOffice "1"-- "*" Ticket
TicketOffice o-- TicketSeller
TicketOffice o-- TicketManager
TicketManager -- TicketScanner
TicketOffice --> PaymentGateway
Ticket "1"-- "*" ITicketScan
ITicketScan --> TicketManager
ITicketScan --> TicketScanner
    
@enduml
```

<img src="https://www.plantuml.com/plantuml/dsvg/hLN1Jjn03BtdAw8zpK8uzBgg41L85HAqLPTRrOD9l3GYCxEQSK2hYd_lXBYDdGchgkeUGiRFVdwsyUGY4WJgRLVieNw41oplsleHQNk8XBRyMPJfLtSG8mDi6dvdfGMgVspAs-6FC4S4sfJRzFnZFELm8qCguRaMhWz8hxXPiwF61lS4JGbUYadc6A1KDa2uAQ_IKnW9mSR4GQ5r3z--I_K4JTlRX8ql8lceQkAhvZHL5ZshQuWowp5Q8tS3arbFN1fcki4XrnKdV9u_-J_vjidxnBZgb0EBlmK8S-TheDQx1QY6FTGj7JPbw-IqcTr8nYeZgdJyh5UVKkpK45akOvASwzGCDvnlcKNWax0ZR9UiTM3JrKO1wehUx3u2wTRtzXw38axMu9_dkOP88xmhTihRz-gp99OXoR9Oy5V_l1W-s3dfhCANOdwFG8TnuHhvlDkrDQeEq2kGbkccZVH-T3lFy5jmYJric8UFGf_aDsiblEj6q8nKpB5GUy1TxvfZplb4kTwK1CFVB1NQVUSFYDTN6NYgoFGEBSIfkGT4kkmZUPiYyyhsmJ-r3LwxdG-MT-DuHTpXXL5jQt1k6WKVHJ95OEAYkvfGChtLz7llkrpY5pXOTFGH29_X83IUpY2praseCKRsC61zxrAknlVt7N8k1AUNWRst1DH7inzFOWXgYceJFjH3jallAFXExOBgX5Al4FCFJU8sjOumxA36ydgY_B-PYcAqbcTd_BKUFy4dwSoV0VOOJGXKg4jWzMwLxAkJ5TDhr2TChaEEwfj0dP8cLQ2EJkZvxF-4SQ59zAqGxqEipfoZAl45kgQttIy0" alt="UML">



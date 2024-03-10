```
@startuml
left to right direction

actor Customer as C
actor TicketSeller as TS
actor TicketScanner as TSc
actor PaymentSystem as PS

rectangle "Point-of-Sale System" {
    usecase "Приобретение билета" as PurchaseTicket
    usecase "Сканирование билета" as ScanTicket
    usecase "Возврат билета" as RefundTicket
    usecase "Обработка платежа" as ProcessPayment

    C --> PurchaseTicket
    PurchaseTicket --> PS : Оплата билета
    PurchaseTicket --> TS : Выбор билета и покупка

    C --> ScanTicket
    ScanTicket --> TSc : Сканирование билета

    C --> RefundTicket
    RefundTicket --> TS : Возврат билета

    PS --> ProcessPayment
}

@enduml
```

<img src="https://www.plantuml.com/plantuml/svg/ZPDFQi905CRtSug7-roWYo9u0UbuWM4SDJIPWPd9Gaf1xB8x3s3f3KR1LYnDh_1oexvCj6Wqq6mUxy_lo_TUIDzvONsHPonJ4m_UW4sdCm_Zr2hfKwCP4z8R2uF2UPCh2yB1u5WRfV9HUQwohAcF-6L32grF7Nbi3SKyLzhpkVCghrj3pbZzBg6dcOBUqAJQ9sQIS45fCzQ39mRq54v9uMW8twe5xh743SLTjSGTVbE-0znG-8gbq8lgXPKpOXf7BPLtF62eIL8fSOkXIwNUvAR2YhXFt18VgkKrzw0cXHxV9DVHUo2af77o0VX3R8ZBV9pSMoELSyURiIWnW2Ivlx5NgzHCSRW3NFyfXmkBNTGeKglgDPfRN320-zfeYOVgXIBvFdVLkbDCptKb2V_hwkUYLqTi2jU6Exy5QpRbSRXrqsV6-agFwp_W5m00" alt="UML">
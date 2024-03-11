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
    usecase "Получение информации" as GetInformation

    C --> PurchaseTicket
    PurchaseTicket --> PS : Оплата билета
    PurchaseTicket --> TS : Выбор билета и покупка

    C --> ScanTicket
    ScanTicket --> TSc : Сканирование билета

    C --> RefundTicket
    RefundTicket --> TS : Возврат билета

    PS --> ProcessPayment

    C --> GetInformation
    GetInformation --> TS : Получение информации
}

@enduml

```

<img src="https://www.plantuml.com/plantuml/svg/ZLDDQi905DxFAGRtkK0NHN1HkfF62mpZH4EJ6PYPBAGKH4kxwCu3M7g3ADYArlGARsxKbqJ5J1NCmk7zVD_xllUmRIpJDaiJaeZ8KgkeZWT3I_kn5jp6IXB2k5MQTZ9ZLIeqPOPszhbUp1-53KMIrFbUs2nm9kMXmlUbBXkbGjfmPAn8or8t9AISnUGW4RJLLR6qWOg2a65OjxNe4w7uPKPmPh09FjmOrb300j-Lcy0ATXYlA2pmsLQfl5MnPveF4LChybW-OGDvYKIM0fQGNs8fdPnbc27k6vQ8pztaF-v1H9didqNEA-qvGWfiHnqKVX6RLsQ-3kgruiAO_Sxy7U3ihPkwjwDx_Dcv5oYG-0UPNZ5ULpntmjxBIEcKrIUb-7Le4DoUsO-Nghj2UaDXVbIODwnUGlKgrCozLoR73GngBGqNi75JVD7_YIf_tsNOuEL8VCNrcgJ-CGu9Nx1_KvyDbu7DtcrE1ldRnhoNEXbstH79Co5j8Vlb__GF" alt="UML">

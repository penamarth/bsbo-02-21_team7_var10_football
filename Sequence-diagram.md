```
@startuml
actor Customer
participant "TicketSeller" as TS
participant "TicketOffice" as TO
participant "PaymentGateway" as PG
participant "TicketScanner" as TSc

Customer -> TO: Приобретение билета
activate TO
TO -> TS: Выбор билета и покупка
activate TS
TS --> TO: Билет продан
TO --> Customer: Билет приобретен
deactivate TS
TO -> PG: Оплата билета
activate PG
PG --> TO: Платеж обработан
TO --> Customer: Оплата проведена
deactivate PG
TO -> TSc: Сканирование билета
activate TSc
TSc --> TO: Билет просканирован
TO --> Customer: Доступ разрешен
deactivate TSc
@enduml
```

<img src="https://www.plantuml.com/plantuml/svg/VL9DIiD05DxFAHxTzm8kfE0YomQI2mpJAGIRj2HJfRiQDu8hnRN56qobqL9fUeKtD_BDc55YeelmoF1zx_kP6HMAvsgPpXWNQfx3nR9GyrJcR477YKWMF5CmY1DnALKaPpEP3u0N44TzWF5qcWZv1HYt0I5VfJ9J0LVocgyS90nwHGJFicyLmPXt1CDpsde6k35ht6EDMvgLAR728_rNW5iQ7-v8spJ95ObP8_7OSIFYFffxWjLctK83xW5FjF9WRcaUMlo8nH4ClVY3Pn61z6lSeSQZao28z_eBs3NC9hAbu1o60V6UyKGyxMpr9wBUmk37qQQ1L_W6ZOXs6SjUPoq57-ALs3jNfFRE6YNVdI3YYst6bjrmzF_5q-NHztTrvgQphy_kaqMQqjuCk6plhiQxRes2ZMGsiM_v4m00" alt="UML">
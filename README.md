# PalcoLivre - Diagrama C4 de Container (nível 2)

![Diagrama de Container](palcolivre-container.png)

Fonte: `palcolivre-container.puml` (C4-PlantUML).

## Justificativas

- **Broker de mensagens (RabbitMQ): requisito 5.** O envio do ingresso pode atrasar alguns segundos, mas nenhum pode deixar de ser emitido. Filas duráveis com reentrega garantem isso, mesmo se o serviço externo falhar.
- **Cache (Redis): requisito 6.** O catálogo é lido com frequência muito maior do que é alterado. Servir as leituras do cache alivia o banco de dados na abertura de vendas (requisito 2).

# **Projeto 3: Time Share de Bens**

---

## **Descrição**
O sistema será uma aplicação que gerencia o modelo de *time share*, onde administradores ofertam bens compartilhados, como quartos de resorts, imóveis ou outros produtos de alto valor, para venda em frações de tempo específicas. Usuários podem adquirir esses direitos de uso e, com base nesses direitos, realizar reservas dentro de um intervalo específico de tempo ou fora dele, pagando uma taxa extra.

### **Exemplo de Funcionamento do Sistema:**

Imagine que um administrador oferece um quarto de hotel por 52 semanas por ano, e cada semana pode ser vendida separadamente. Quando o usuário compra uma fração de tempo, ele adquire **o direito de usar o bem por uma semana específica do ano**, mas essa semana é **móvel**, o que significa que a data dessa semana vai mudar a cada ano.

#### **Funcionamento da Compra e Reserva:**
1. **Compra**: O usuário compra uma fração de 1/52 semanas do bem, o que significa que ele tem o direito de usar uma semana específica do ano. Por exemplo, se ele comprar a **semana 1** (de 1 a 7 de março) em 2024, ele terá direito de usar o quarto nessas datas.
2. **Móvel no Ano Seguinte**: No próximo ano, a sua **semana 1** será automaticamente deslocada para o período correspondente em 2025, ou seja, de **8 a 15 de março**, e em 2026 a **semana 1** será de **16 a 23 de março**, e assim por diante. Esse deslocamento garante que todos os compradores, independentemente da semana que adquiriram, possam usar todas as semanas ao longo do tempo.

3. **Reserva Dentro do Período**: O usuário pode fazer uma reserva para a semana correspondente ao seu direito de uso no ano vigente, sem custos adicionais. Por exemplo, se ele comprou a fração para usar de 1 a 7 de março de 2024, ele pode fazer a reserva para esse período sem taxas extras.

4. **Reserva Fora do Período**: Caso o usuário queira reservar um período fora da sua fração de semana adquirida, por exemplo, uma semana diferente do seu direito de uso, ele poderá fazer a reserva, mas estará sujeito a **taxas extras**. Essas taxas são aplicadas quando o usuário tenta reservar um período fora da sua janela de tempo contratada.

5. **Revenda ou Transferência de Direitos**: Caso o usuário não deseje usar sua fração de semana comprada, ele poderá **revender ou transferir** esse direito para outro usuário dentro do sistema. O comprador da fração adquirirá o direito de usar a **semana móvel** correspondente no ano seguinte.

### **Resumo do Funcionamento:**
- O usuário compra **uma semana específica** em um ano determinado, mas essa semana será **móvel**, ou seja, no ano seguinte ela será deslocada para o período correspondente no calendário do novo ano.
- As **semanas subsequentes** se movem para garantir que todos os usuários tenham acesso a todas as semanas ao longo do tempo.
- O usuário pode **reservar** sua semana correspondente sem custos extras, e **reservas fora do período** têm taxas adicionais.
- **Revenda ou transferência** de frações de tempo podem ser realizadas entre usuários dentro do sistema.

Este modelo de *time share* oferece uma forma justa e equilibrada de dividir o uso de bens de alto valor entre múltiplos usuários ao longo dos anos, permitindo que todos tenham a chance de usar todas as semanas ao longo do tempo. O administrador gerencia as frações e as reservas, enquanto os usuários podem usufruir do bem de acordo com as regras estabelecidas.

---

## **Requisitos Funcionais**

### **Gerenciamento de Entidades**
- **REQ01**: Gerenciamento de administradores, que podem cadastrar e ofertar bens para venda.
- **REQ02**: Gerenciamento de bens ofertados, incluindo informações como nome, descrição, capacidade de uso (ex.: número de pessoas), localização, preço e frações disponíveis para venda.
- **REQ03**: Gerenciamento de usuários, que podem adquirir direitos de uso, realizar reservas e revender direitos.
- **REQ04**: Registro de direitos de uso adquiridos por usuários, incluindo informações como bem associado, fração comprada (ex.: 1/52) e período móvel correspondente ao ano atual.

### **Operações de Venda**
- **REQ05**: Compra de frações de bens, com controle automático de disponibilidade de frações e do deslocamento anual da semana adquirida.
- **REQ06**: Transferência ou revenda de direitos de uso entre usuários cadastrados, com atualização dos registros.

### **Operações de Reserva**
- **REQ07**: Consulta de períodos disponíveis para reserva, considerando o deslocamento da fração adquirida a cada ano.
- **REQ08**: Criação de reservas gratuitas dentro do intervalo permitido pelo direito adquirido, respeitando o período correspondente à fração comprada.
- **REQ09**: Criação de reservas fora do intervalo permitido, aplicando automaticamente uma taxa extra calculada com base no período.
- **REQ10**: Cancelamento de reservas pelos usuários ou administradores.

### **Consultas e Relatórios**
- **REQ11**: Consulta ao histórico de uso de um bem, incluindo reservas realizadas por diferentes usuários.
- **REQ12**: Relatório de disponibilidade de um bem em períodos futuros, considerando frações ainda não vendidas e reservas pendentes.
- **REQ13**: Estatísticas de vendas e reservas por bem, incluindo frações mais populares e períodos mais reservados.

### **Validações e Controle**
- **REQ14**: Validação automática de conflitos de datas para reservas e controle de taxas adicionais para períodos fora do intervalo permitido.
- **REQ15**: Ajuste automático do deslocamento da fração de semanas no início de cada ano (ex.: a fração de uma semana de 2024, de 1 a 7 de março, passará para 8 a 15 de março em 2025, e assim sucessivamente).

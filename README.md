# Projeto-Mobile-20261

## Funcionalidade: Reservar Espaço

**Como** um morador do condomínio  
**Ou** um administrador do condomínio  
**Eu quero** visualizar a disponibilidade e agendar um horário nas quadras  
**Para** algum evento  

### Cenário 1: Reserva com Sucesso

**Dado** que selecionei a "Quadra Poliesportiva" e um horário disponível no dia 17 de Março  
**E** meu status financeiro no condomínio está "Regular"  
**Quando** eu confirmar a reserva  
**Então** o sistema deve debitar a reserva da minha cota e exibir a mensagem "Reservado com sucesso"  

### Cenário 2: Bloqueio por Inadimplência 

**Dado** que possuo pendências financeiras com o condomínio  
**Quando** eu tentar selecionar um horário  
**Então** o sistema deve exibir um aviso: "Reservas bloqueadas. Entre em contato com a administração" e impedir a conclusão  

### Cenário 3: Conflito de Horário

**Dado** que um horário acabou de ser reservado por outro usuário enquanto eu navegava  
**Quando** eu clicar em reservar  
**Então** o sistema deve validar a disponibilidade e informar que o horário não está mais disponível  

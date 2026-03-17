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
  
**AC 01:** O sistema deve permitir reservas apenas com antecedência mínima de 24 horas e máxima de 30 dias  
**AC 02:** Cada apartamento possui uma cota máxima de 3 reservas ativas simultâneas  
**AC 03:** O tempo padrão de reserva para qualquer espaço é de 60 minutos, iniciando sempre em hora cheia  

### Cenário 2: Bloqueio por Inadimplência 

**Dado** que possuo pendências financeiras com o condomínio  
**Quando** eu tentar selecionar um horário  
**Então** o sistema deve exibir um aviso: "Reservas bloqueadas. Entre em contato com a administração" e impedir a conclusão  
  
**AC 04:** Usuários com status inadimplente: true no banco de dados devem ter o botão de "Confirmar Reserva" desabilitado  
**AC 05:** O sistema deve validar a disponibilidade no servidor no momento do clique, antes de processar o pagamento ou confirmação  
**AC 06:** Administradores podem realizar reservas ignorando as travas de inadimplência e cota  

### Cenário 3: Conflito de Horário

**Dado** que um horário acabou de ser reservado por outro usuário enquanto eu navegava  
**Quando** eu clicar em reservar  
**Então** o sistema deve validar a disponibilidade e informar que o horário não está mais disponível  
  
**AC 07:** Horários já ocupados devem aparecer visualmente distintos e não devem ser clicáveis  
**AC 08:** Após a confirmação, o usuário deve receber um e-mail ou notificação push com o comprovante da reserva  
**AC 09:** Deve haver um botão de "Cancelar Reserva" disponível até 2 horas antes do horário agendado  

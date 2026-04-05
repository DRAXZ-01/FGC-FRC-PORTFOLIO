# FRC Control Systems

Implementação de um sistema de controle para drivetrain diferencial desenvolvido na FRC, com foco em seguimento de trajetória, caracterização do sistema e simulação.


## Visão Geral

Este projeto tem como objetivo melhorar o desempenho do robô através de:

- Seguimento de trajetórias com PathPlanner  
- Caracterização do sistema com SysId  
- Estimativa de pose com visão (AprilTags)  
- Simulação física do drivetrain  
- Simulação de um mecanismo de elevador  

A proposta é tornar o comportamento do robô mais previsível e consistente durante a execução de trajetórias.


## Principais Componentes

### Controle de Trajetória (PathPlanner)
- Controle baseado em velocidade 
- Uso combinado de feedforward e PID  
- Aumento da consistência na execução de paths  

### System Identification (SysId)
- Caracterização do drivetrain  
- Obtenção de constantes de feedforward  
- Aplicação direta no controle de trajetória  


### Visão (AprilTags)
- Estimativa de pose do robô  
- Filtragem de medições por ambiguidade  
- Ajuste dinâmico da confiança com base na distância  


### Simulação
- Simulação de drivetrain com WPILib  
- Simulação de elevador baseada em modelo físico  
- Validação de comportamento sem necessidade de hardware

### AutoAlign
- Cálculo dinâmico do ângulo até o alvo com base na pose do robô  
- Uso de `atan2` para determinar a direção correta independente da posição no campo  
- Controle de rotação com PID para alinhamento automático  

### Telemetria e Debug (Logger)
- Uso de logging estruturado para monitorar:
  - posição do robô  
  - velocidade das rodas  
  - tensão aplicada nos motores  
- Permitiu identificar inconsistências no comportamento do drivetrain durante testes  

### Arquitetura de Motores (YAMS)
- Abstração dos controladores de motor para simplificar a criação de subsistemas  
- Padronização de configuração (corrente, inversão, gearing, etc.)  
- Facilita manutenção e reaproveitamento de código entre diferentes mecanismos  


##  Resultados

- Redução do erro angular nas trajetórias (de ~30–40° para ~10°)  
- Maior consistência na execução dos paths  
- Melhor previsibilidade do comportamento do robô  


##  Observações

Este projeto é uma versão simplificada baseada no código real do robô, com foco em demonstrar conceitos de controle, simulação e modelagem de sistemas.

# SmartVest: Sistema de Acionamento de Airbag para Motociclistas

## Sobre o Projeto
Projeto de desenvolvimento de um sistema embarcado para acionamento de airbag em coletes de motociclistas. O sistema utiliza um microcontrolador **STM32** e uma unidade de medição inercial (**IMU**) para monitorar a cinemática do usuário em tempo real, aplicando algoritmos de filtragem de ruído e drift para detectar padrões de colisão ou queda e acionar o sistema de inflação. 

Este projeto tem foco acadêmico e potencial para futura pesquisa e aplicação.


## 👥 Divisão da Equipe
Para otimizar o desenvolvimento, as etapas de desenvolvimentos foram dividas nas seguintes frentes(as quais não necessariamente acontecem em serie):
*   **Engenharia de Firmware & Controle:** Desenvolvimento do código no STM32, configuração de periféricos (I2C/SPI para a IMU) e gerenciamento de interrupções.
*   **Processamento de Sinais & Algoritmos:** Implementação de filtros de ruído (ex: Filtro de Kalman ou Madgwick) e modelagem da lógica de detecção de acidentes.
*   **Hardware & Eletrônica de Potência:** Projeto esquemático, layout da PCB e circuito de acionamento (ignição) do atuador do airbag.
*   **Testes & Integração:** Condução de ensaios de simulação de impacto, coleta de dados telemétricos e validação do tempo de resposta.


## 🔄 Gestão do Repositório (Git Workflow)
Adotamos um fluxo baseado no **GitFlow** para manter a organização do código:
*   `main`: Código estável, testado e funcional. Protegida contra commits diretos.
*   `develop`: Branch principal de integração de desenvolvimento.
*   `feature/nome-da-funcionalidade`: Branches criadas a partir da `develop` para desenvolver novos recursos (ex: `feature/imu-kalman-filter`).
*   `bugfix/nome-do-bug`: Branches para correção de erros não críticos.


**Padrão de Commits:** Utilizaremos commits semânticos (ex: `feat: configura I2C do STM32`, `fix: corrige overflow na leitura do giroscópio`, `docs: atualiza pinout no README`).


## 🎯 Milestones (Marcos do Projeto)
- [ ] **M1: Setup e Aquisição de Dados:** Configuração do ambiente STM32, comunicação com a IMU e leitura bruta (raw) dos dados de aceleração e rotação.
- [ ] **M2: Processamento e Filtragem:** Implementação e calibração dos filtros de ruído da IMU para obter orientação e aceleração lineares confiáveis.
- [ ] **M3: Algoritmo de Detecção:** Desenvolvimento e calibração dos limiares (thresholds) matemáticos para identificar quedas e impactos sem falsos positivos.
- [ ] **M4: Acionamento e Hardware:** Integração da lógica com o circuito de potência para disparo do atuador do airbag e finalização do projeto da PCB.
- [ ] **M5: Testes e Validação:** Ensaios práticos de bancada e elaboração da documentação final para submissão a bolsas de pesquisa.

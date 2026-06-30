Nome do projeto:
MonitorNet

Integrantes:
- João Vitor

Tema escolhido:
Monitoramento de conectividade de rede

Objetivo do sistema:
O MonitorNet tem como objetivo verificar se a VM Linux está conectada corretamente
à rede e à internet. O sistema mostra informações básicas da máquina, identifica
endereços IP, gateway padrão, interfaces de rede e testa a conexão com a internet
e com sites específicos.

Problema que o sistema resolve:
Em uma VM Linux, problemas de rede podem acontecer por falta de IP, ausência de
gateway, interface incorreta ou falha de conexão externa. O sistema automatiza
essa verificação e gera um relatório simples para consulta.

============================================================
COMO EXECUTAR
============================================================

1. Abrir o terminal na pasta do projeto:

   cd projeto_linux

2. Dar permissão de execução ao script:

   chmod +x sistema.sh

3. Executar o sistema:

   ./sistema.sh

Também é possível executar usando bash:

   bash sistema.sh

============================================================
PRINCIPAIS FUNCIONALIDADES
============================================================

1. Exibe data, hora, hostname e usuário atual.
2. Lista as interfaces de rede da máquina.
3. Mostra os endereços IP configurados.
4. Identifica o gateway padrão.
5. Testa conexão com a internet usando ping para 8.8.8.8.
6. Verifica disponibilidade de sites como google.com e github.com.
7. Gera um relatório final em arquivo .txt.
8. Registra eventos de execução em arquivo de log.
9. Mantém histórico acumulado das execuções.
10. Faz backup automático do log e do relatório.

============================================================
COMANDOS LINUX USADOS
============================================================

date      - registrar data e hora da execução
hostname  - mostrar o nome da máquina
whoami    - mostrar o usuário atual
ip addr   - listar os endereços IP
ip route  - identificar o gateway padrão
ip link   - listar interfaces de rede
ping      - testar conexão com internet e sites
grep      - filtrar informações importantes
awk       - organizar a saída dos comandos
sed       - ajustar o nome das interfaces exibidas
echo      - exibir mensagens e escrever nos arquivos
cp        - copiar logs e relatórios para backup
chmod     - dar permissão de execução ao script

============================================================
ESTRUTURA DO PROJETO
============================================================

projeto_linux/
├── sistema.sh              <- script principal do sistema
├── README.txt              <- explicação do projeto
├── logs/
│   └── sistema.log         <- log das execuções
├── relatorios/
│   └── relatorio_rede.txt  <- relatório da última execução
├── dados/
│   └── historico.txt       <- histórico acumulado
└── backup/
    └── cópias automáticas de logs e relatórios

============================================================
LOGS
============================================================

O log principal fica em:

   logs/sistema.log

Esse arquivo registra os eventos principais do sistema, como início da execução,
resultado do teste de internet, geração do relatório, backup e finalização.

Exemplo de registros:

   [30/06/2026 10:36:16] Projeto iniciado.
   [30/06/2026 10:36:16] Teste de internet: SUCESSO.
   [30/06/2026 10:36:16] Relatório gerado em relatorios/relatorio_rede.txt.
   [30/06/2026 10:36:16] Execução finalizada.

============================================================
RELATÓRIO GERADO
============================================================

O relatório final fica em:

   relatorios/relatorio_rede.txt

Ele apresenta:

- data e hora da verificação;
- hostname da VM;
- usuário atual;
- endereços IP encontrados;
- gateway padrão;
- interfaces de rede;
- resultado do teste de internet;
- status dos sites testados.

O sistema também atualiza o histórico em:

   dados/historico.txt

E cria cópias automáticas na pasta:

   backup/

============================================================
CRONTAB
============================================================

O projeto demonstra o uso do crontab por meio de uma linha sugerida de
agendamento. Em uma VM Linux com cron instalado, o sistema poderia ser executado
automaticamente a cada 10 minutos com a seguinte configuração:

   */10 * * * * bash /caminho/projeto_linux/sistema.sh >> /caminho/projeto_linux/logs/sistema.log 2>&1

Também poderia ser executado uma vez por dia às 08h:

   0 8 * * * bash /caminho/projeto_linux/sistema.sh >> /caminho/projeto_linux/logs/sistema.log 2>&1

Para configurar em uma VM Linux real:

   crontab -e

Para listar tarefas agendadas:

   crontab -l

Observação:
No GitHub Codespaces, o comando crontab pode não estar disponível porque o
ambiente é um container temporário. Por isso, neste projeto o crontab é
demonstrado por meio da linha sugerida acima e explicado na apresentação.

============================================================
O QUE CADA INTEGRANTE FEZ
============================================================

João Vitor:
- desenvolveu o script principal sistema.sh;
- organizou a estrutura de pastas do projeto;
- implementou os testes de rede;
- configurou a geração de log;
- configurou a geração de relatório;
- implementou o backup automático;
- documentou a simulação de uso do crontab.

============================================================
OBSERVAÇÃO FINAL
============================================================

Antes da entrega, testar com:

   chmod +x sistema.sh
   ./sistema.sh

Depois conferir se os arquivos abaixo foram criados ou atualizados:

   logs/sistema.log
   relatorios/relatorio_rede.txt
   dados/historico.txt
   backup/

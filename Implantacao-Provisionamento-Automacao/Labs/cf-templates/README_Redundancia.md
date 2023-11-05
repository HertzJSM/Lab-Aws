1. **VPC (Virtual Private Cloud):**
   - Cria uma VPC com a faixa de endereços IP definida em CIDR: 10.0.0.0/16.
   - Ativa o suporte DNS e nomes de DNS para a VPC.

2. **Subnet Pública:**
   - Cria uma sub-rede pública dentro da VPC com a faixa de endereços IP: 10.0.0.0/24.
   - Associa um grupo de segurança à sub-rede que permite tráfego SSH (porta 22) e HTTP (porta 80) de qualquer origem.

3. **Internet Gateway:**
   - Cria um Internet Gateway que permite que a VPC acesse a internet.

4. **Rota Pública:**
   - Define uma rota padrão na tabela de rotas da VPC para direcionar todo o tráfego (0.0.0.0/0) para o Internet Gateway.

5. **ACL (Access Control List) de Rede Pública:**
   - Cria uma ACL de rede para a VPC que permite o tráfego de entrada na porta 80 (HTTP) e saída em todas as portas.

6. **Instância EC2 (Primeira):**
   - Cria uma instância EC2 na sub-rede pública da VPC.
   - A instância utiliza o tipo especificado no parâmetro (por padrão, t3.micro).
   - Instala o servidor web Apache (httpd) e exibe uma página HTML simples com uma mensagem.

7. **Grupo de Segurança EC2 (Primeiro):**
   - Cria um grupo de segurança EC2 que permite o tráfego SSH (porta 22) e HTTP (porta 80) de qualquer origem.

8. **Instância EC2 (Segunda - Grafana):**
   - Cria uma segunda instância EC2 na sub-rede pública da VPC.
   - Utiliza o mesmo tipo de instância especificado no parâmetro.
   - Atualiza a lista de pacotes, instala o Grafana e inicia o serviço do Grafana.
   - Não está completa a configuração do Grafana.

9. **Aqui estão algumas etapas comuns que você pode adicionar ao seu código:**

10. **Configuração de Banco de Dados:**
    - Configure o Grafana para se conectar ao seu banco de dados. Você pode definir as credenciais, o tipo de banco de dados (por exemplo, MySQL, PostgreSQL, InfluxDB) e outros parâmetros relevantes.

11. **Configuração de Fontes de Dados:**
    - Adicione as fontes de dados que o Grafana usará para coletar métricas e dados. Isso pode incluir configurações de Prometheus, Elasticsearch, AWS CloudWatch, etc.

12. **Configuração de Dashboards e Painéis:**
    - Crie e importe dashboards e painéis para visualizar os dados coletados. Você pode especificar modelos, gráficos, alertas e outras configurações específicas.

13. **Configuração de Notificações e Alertas:**
    - Defina notificações e alertas para serem acionados com base em métricas específicas. Isso pode incluir configurações de envio de e-mails, integração com serviços de mensagens, como Slack, e muito mais.




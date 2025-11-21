
## PLANO DE TESTES –  MÓDULO VISÃO GERAL DO FUNCIONARIO (SmartCondo)

1. Identificação

| Item            | Descrição                        |
| --------------- | -------------------------------- |
| **Sistema**     | SmartCondo                       |
| **Módulo**      | VISÃO GERAL DO FUNCIONARIO |
| **Responsável** | ANNA CLARA                       |
| **Versão**      | 1.0                              |
| **Data**        | 21/11/2025                       |

2. Validar todo o funcionamento da página de Visão Geral do Funcionario, assegurando que cada módulo do dashboard esteja operando corretamente e apresentando informações consistentes. A verificação deve contemplar:

- Ordem de Serviços: Garantir que cada Ordem de Serviço exiba corretamente:

- Ano e data da solicitação

- Título

- Categoria

- Status (Aberta, Concluída ou Em andamento)

- Prioridade (Baixa, Média ou Alta)

- Ação Ver, permitindo abrir os detalhes da OS contendo:

- Número da OS

- Prioridade

- Título

- Ocorrência vinculada (quando aplicável)

- Data sugerida para realização

- Responsável pela execução

- Local da execução

- Descrição completa
  
- Botões Iniciar, Voltar e Concluir

- Ocorrências: Verificar o funcionamento dos módulos:

- Solicitações/Ocorrências abertas

- Minhas Ocorrências, com separação entre Pendentes e Resolvidas

- Comunicados: Confirmar que o sistema apresenta corretamente:

- Lista de comunicados recentes

- Mensagens enviadas e recebidas

- Funcionalidades Gerais do Dashboard: Assegurar:

- Identificação correta do usuário logado

- Exibição atualizada de solicitações/ocorrências abertas

- Persistência e consistência de todos os dados exibidos


3. Ambiente de Testes

- Ambiente de execução: Localhost (Live Server) ou ambiente de homologação

- Navegadores utilizados: Chrome versão 140 ou superior, Firefox e Microsoft Edge

- Armazenamento de dados: localStorage e sessionStorage

- Arquivos envolvidos: dashboard.html, index.js, auth/logout.js

- Usuário utilizado nos testes: Funcionário previamente autenticado e armazenado no sessionStorage

4. Casos de Teste

<table>
 <tr>
  <th>Identificação</th>
  <th>Objetivo</th>
  <th>Ambiente de Teste</th>
  <th>Passos</th>
  <th>Critérios de Êxito</th>
  <th>Responsável</th>
 </tr>

 <!-- CT-01 -->
 <tr>
  <td><strong>CT-01 — Exibir nome e cargo do usuário logado</strong></td>
  <td>Verificar se o nome “Marcos de Souza, Zelador” (usuário padrão de teste do sistema) está sendo exibido corretamente.</td>
  <td>Web / Funcionário logado / SessionStorage ativo</td>
  <td>
   <ol>
    <li>Efetuar login como funcionário.</li>
    <li>Acessar a página “Visão Geral”.</li>
   </ol>
  </td>
  <td>O elemento #usuarioLogado deve exibir: <em>“Marcos de Souza, Funcionário”</em>.</td>
  <td>Anna Clara</td>
 </tr>

 <!-- CT-02 -->
 <tr>
  <td><strong>CT-02 — Exibir Ordem de serviço</strong></td>
  <td>Validar se o card exibe as (OS) corretamente.</td>
  <td>Web / LocalStorage com chave "smartcondo_ocorrencias"</td>
  <td>
   <ol>
    <li>Popular o localStorage com Ocorrências.</li>
    <li>Acessar a página do dashboard.</li>
   </ol>
  </td>
  <td>O card “Ordem de Serviço” exibe exatamente o total de OS salva em storage.</td>
  <td>Anna Clara</td>
 </tr>

 <!-- CT-03 -->
 <tr>
  <td><strong>CT-03 — Exibir Ocorrências</strong></td>
  <td>Validar se o card exibe corretamente as minhas ocorrências.</td>
  <td>Web / LocalStorage chave “smartcondo_ocorrencias”</td>
  <td>
   <ol>
    <li>Exibir Ocorrências em aberto/concluídas.</li>
    <li>.Registrar nova ocorrência</li>
   </ol>
  </td>
  <td>O card “Ocorrências” exibe a quantidade correta.</td>
  <td>Anna Clara</td>
 </tr>

 <!-- CT-04 -->
 <tr>
  <td><strong>CT-04 — Enviar Comunicados</strong></td>
  <td>Verificar se os comunicados são mantidas após recarregar a página..</td>
  <td>Web / LocalStorage com chave “smartcondo_ocorrencias”</td>
  <td>
   <ol>
    <li>Enviar comunicados com status variados.</li>
    <li>Carregar a página.</li>
   </ol>
  </td>
  <td>O card deve exibir os comunicados enviados.</td>
  <td>Anna Clara</td>
 </tr>

 <!-- CT-05 -->
 <tr>
  <td><strong>CT-05 — Mensagens recebidas/Enviadas</strong></td>
  <td>Verificar se as mensagens são mantidas após recarregar a página.</td>
  <td>Web / LocalStorage com chaves “smartcondo_ocorrencias”</td>
  <td>
   <ol>
    <li>O card deve exibir as mensagens enviadas e recebidas.</li>
    <li>Carregar a página.</li>
   </ol>
  </td>
  <td>O card “mensagem recebidas” e “mensagem enviadas” exibir as mensagens enviadas e recebidas apenas.</td>
  <td>Anna Clara</td>
 </tr>

 <!-- CT-06 -->
 <tr>
  <td><strong>CT-10 — Logout do sistema</strong></td>
  <td>Validar se o botão de logout executa o método logout().</td>
  <td>Web / SessionStorage ativo</td>
  <td>
   <ol>
    <li>Clicar no botão de logout.</li>
   </ol>
  </td>
  <td>O usuário é redirecionado para a página de login e sessionStorage é limpo.</td>
  <td>Anna Clara</td>
 </tr>

</table>

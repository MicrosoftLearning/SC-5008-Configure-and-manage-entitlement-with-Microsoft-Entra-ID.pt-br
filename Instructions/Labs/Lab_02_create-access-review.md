---
lab:
  title: 'Laboratório 2: – Criar e gerenciar uma Revisão de acesso'
  module: 'Module : Deploying access using Microsoft Entra entitlement management'
---

# Laboratório 2: Criar e gerenciar uma Revisão de acesso

## Cenário do laboratório

As revisões de acesso ajudam a garantir que apenas as pessoas certas possam acessar os recursos e as informações. Uma revisão de acesso pode ser configurada para períodos recorrentes ou uma única vez, e permite que os revisores aprovem ou neguem o acesso com base em fatores como função do usuário, última entrada ou nível de risco. Os resultados dessas revisões podem ser usados para atualizar os direitos de acesso do usuário, garantindo que eles estejam alinhados às políticas da empresa e aos requisitos de conformidade. Para esta empresa, eles usam uma revisão de acesso quando um funcionário muda de função dentro de uma empresa. Por exemplo, se um funcionário mudar de uma função de vendas para uma função de marketing, talvez o usuário não precise mais de acesso a determinados bancos de dados ou aplicativos de vendas. Uma revisão de acesso ajudaria a identificar essas permissões desnecessárias e permitiria que a empresa as revogasse, reduzindo assim o risco de acesso não autorizado ou vazamento de dados.

#### Tempo estimado: 15 minutos

### Exercício 1 – Confirme se nenhum usuário está acessando o LinkedIn que não deveria estar usando esse recurso.

#### Tarefa 1 – Criar uma Revisão de acesso – Tipo de Revisão

1. Entre no [https://entra.microsoft.com](https://entra.microsoft.com) usando uma conta de administrador global.

1. Abra o menu **Identidade** e selecione  **Governança de Identidade**.

1. No menu à esquerda, clique em **Revisões de acesso**.

1. No menu à esquerda, clique em **+ Nova revisão de acesso**.

1. No painel Nova revisão de acesso, clique no item **Aplicativos** na lista suspensa "Selecionar o que revisar".

1. Use **+ Selecionar aplicativo(s)** para escolher o **LinkedIn** na lista.

1. Em **Escopo**, selecione **Todos os usuários**.

1. Clique no botão **Avançar: Revisões** na parte inferior da tela.

#### Tarefa 2 – Criar uma Revisão de acesso – Revisões

1. Marque temporariamente a caixa **Revisão em vários estágios** com uma verificação.

 **Observação** – É aqui que você pode optar por ter várias camadas para sua Revisão de acesso.  Use isso para recursos muito importantes, para que a revisão de uma única pessoa não adicione ou remova um recurso crítico do acesso do usuário.  Não vamos construir/testar uma revisão em vários estágios, mas o processo é muito semelhante.

1. Desmarque a caixa **Revisão em vários estágios**.

1. Preencha a página Revisão com os valores abaixo:

| Nome do campo | Valor |
| :--- | :--- |
| Selecionar os revisores | Selecione o(s) usuário(s) ou grupo(s) – Adele Vance |
| Duração (em dias) | 5 |
| Revisão de recorrência | Mensal |
| Data inicial | Data atual |
| Término | Terminar após o número de ocorrências |
| Ocorrências | 3 |
| | |

1. Clique na opção **Avançar: Configurações**.

#### Tarefa 3 – Criar uma Revisão de acesso – Configurações

1. Deixe a caixa **Aplicar resultados automaticamente aos recursos** no estado desmarcado.

 **Observação** – queremos ter certeza de validar os resultados após a conclusão da revisão.

1. Escolha a opção **Remover acesso** para o **Se o revisor não responder**.

 **Observação** – você pode usar essa configuração para controlar o nível de segurança.  Se nenhuma revisão responder em uma postura de segurança menos segura, você pode escolher Aprovar acesso.  Em uma postura de segurança muito segura, você pode usar o comando Remover acesso.  Ao implementar suas próprias soluções, escolha o que funciona melhor para sua empresa.

1. Em **No final da revisão, enviar uma notificação para**, selecione a conta de administrador que você está usando neste laboratório.

1. Deixe **Ativar auxiliares de decisão de revisão** com o valor padrão.

1. Defina o **Conteúdo adicional para o email do revisor ** e insira o valor `Please complete your Access Review as soon as you can.`

1. Clique em **Avançar: Revisar + Criar**.

1. Insira os valores abaixo para nome e descrição:

| Nome do campo | Valor |
| :--- | :--- |
| Nome da revisão | `Check LinkedIn` |
| Descrição | `In this access review, we check to see if the right people have access to LinkedIn.` |
| | | 

1. Selecione **Criar**.

#### Tarefa 4 – Entrar como Adele para executar a Revisão de acesso

1. Feche o navegador se estiver aberto.

1. Abra o navegador e conecte-se a `https://outlook.office.com/`.

1. Será solicitado que você altere a senha assim que fizer login como Adele.

1. Entre como Adele Vance com base no seu locatário.

 **Observação** – Você terá um email da **Segurança da Microsoft** com o assunto **Ação necessária: Revise o acesso ao LinkedIn...**. Este e-mail pode chegar em até dez minutos.

1. Clique no botão **Iniciar revisão >**.

 ![Captura de tela da página Revisão de acesso que AdeleV vê ao iniciar o link no email.  Observe que é recomendado excluir Christopher Green.](./Media/access-review-page.png)

1. Marque o círculo ao lado de **Christopher Green**.

1. Clique na opção **Negar** no menu superior.

1. Insira um motivo para negar o acesso ao recurso. Exemplo: `The sales campaign is over and Christopher does not need access any more`.

1. Clique no botão **Enviar** para enviar sua recomendação.

#### Tarefa 5 – Confirmar os resultados da Revisão de acesso

1. Feche o navegador se estiver aberto.

1. Abra o navegador e conecte-se a `https://Entra.Microsoft.com/`.

1. Entre no Microsoft Entra com sua conta de administrador.

1. No menu esquerdo, abra **Governança de Identidade**.

1. Escolha **Revisões de acesso**.

1. Escolha a revisão **Verificar LinkedIn ** que criamos anteriormente neste laboratório.

1. Revise a resposta de AdeleV.

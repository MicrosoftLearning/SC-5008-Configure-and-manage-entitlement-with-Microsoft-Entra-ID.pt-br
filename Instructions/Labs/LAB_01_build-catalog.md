---
lab:
  title: 'Laboratório 01: criação de um catálogo para uso no direito'
  module: 'Module : Deploying access using Microsoft Entra entitlement management'
---

# Laboratório 01: criação de um catálogo no gerenciamento de direitos do Microsoft Entra

## Cenário do laboratório

Em uma empresa de desenvolvimento de software de médio porte, o departamento de TI decide implementar o Microsoft Entra para gerenciamento de direitos. O objetivo principal é simplificar o acesso a recursos e aplicativos em toda a organização. Com o Microsoft Entra, eles podem definir pacotes de acesso com base em funções ou projetos, o que simplifica o processo de concessão ou revogação de direitos de acesso. Por exemplo, quando um novo desenvolvedor ingressa em um projeto, o departamento de TI pode facilmente fornecer a ele o acesso necessário, atribuindo-o ao pacote de acesso correspondente. Isso não apenas economiza tempo, mas também reduz o risco de acesso não autorizado. Além disso, as revisões periódicas de acesso do Microsoft Entra garantem que apenas as pessoas certas tenham acesso a recursos confidenciais. No laboratório de implementação, a equipe de TI configurará vários pacotes de acesso, definirá políticas para atribuição e revogação automática de acesso e conduzirá uma revisão de acesso simulada.

## Objetivos

Após concluir este laboratório, você poderá:

- Criar um catálogo.
- Configurar um perfil de acesso.
- Implantar um pacote de acesso para um usuário.
- Aceitar o direito como usuário e confirme o acesso ao recurso.
- Revogar o acesso a um pacote.

## Configuração do Laboratório
  - **Tempo estimado**: 30 minutos

### Exercício 1: criar um catálogo para a equipe de vendas

#### Tarefa 1: criar um catálogo

1. Inicie o centro de administração do Microsoft Entra em `https://Entra.Microsoft.com`.

1. No menu à esquerda, navegue até **Governança de identidade** e, em seguida, **Gerenciamento de direitos**.

1. Selecione **Catalogos** no menu.

 ![Captura de tela da tela de criação de novo catálogo com o botão novo catálogo destacado.  Os campos disponíveis são nome, descrição e habilitado.](./Media/create-new-catalog.png)

1. Selecione **+ Novo catálogo** na parte superior da tela.

1. No **novo catálogo**, dê o nome e adicione a descrição de acordo com os seguintes valores:

  | Campo | Valor |
  | :---  | :---  |
  | Nome  | `catSales` |
  | Descrição | `Use this catalog to assign resources for memebers of the Sales team.` |
  | Habilitado | Sim |
  | Habilitado para usuários externos | Não |
  | | |

1. Selecione **Criar**.

#### Tarefa 2: adicionar recursos ao catálogo

1. Se você ainda não estiver lá, navegue até o **centro de administração do Microsoft Entra**, **Governança de identidade**, **Gerenciamento de direitos** e, em seguida, a página **Catálogos**.

1. Selecione o **catSales** que criamos na tarefa anterior.

1. Selecione **Recursos** no menu.

1. Na parte superior da página, selecione **+ Adicionar recursos**.

 ![Captura de tela do Adicionar recursos à interface do usuário do catálogo. Você pode adicionar Teams, Aplicativos, SharePoints e outros itens.](./Media/add-resources-to-catalog.png)

1. Usando os seletores na parte superior da tela, adicione os seguintes recursos:

  | Tipo de recurso | Valor |
  | :---  | :---  |
  | + Grupos e equipes  | Vendas e Marketing e Vendas nos EUA |
  | + Aplicativos | LinkedIn |
  | + Sites do SharePoint | Vendas e Marketing e Vendas nos EUA |
  | | |

1. Selecione o botão **Adicionar**.

#### Tarefa 3: criar um novo usuário para receber o direito

1. Navegue até o **centro de administração do Microsoft Entra**, caso ainda não estiver nele.

1. No menu à esquerda, selecione **Identidade**, **Usuário** e, em seguida, **Todos os usuários** nos menus.

1. Na parte superior da página, selecione **+ Novo usuário**.

1. Preencha os valores na página **Conceitos básicos**:

  | Campo | Valor |
  | :---  | :---  |
  | Nome UPN  | `ChrisGr` |
  | Nome de exibição | `Christopher Green` |
  | Gerar senha automaticamente | Marcado como habilitado |
  | Conta habilitada | Marcado como habilitado |
  | | |

1. Copie e cole a "Senha" em um local seguro, como o Bloco de notas (você precisará dessa senha posteriormente neste laboratório).

1. Clique na guia "Propriedades".

1. Na parte inferior da tela Propriedades, defina o **Local de uso como Estados Unidos**.

1. Selecione **Revisar + Criar** e então, selecione **Criar**.

#### Tarefa 4: gerar o pacote de acesso

1. No centro de administração do Microsoft Entra, selecione **Governança de identidade** e, em seguida, **Gerenciamento de direitos**.

1. No menu de Gerenciamento de direitos, selecione **Pacotes de acesso**.

1. Selecione **+ Novo pacote de acesso** na parte superior da tela.

1. Insira os valores solicitados:

  | Campo | Valor |
  | :---  | :---  |
  | Nome  | `pckSales` |
  | Nome de exibição | `Use this access package to assign resources to members of the Sales team.` |
  | Catálogo | catSales |
  | | |

  **Observação**: você deve escolher o catálogo catSales que criamos na tarefa anterior. Isso fornecerá a lista de recursos disponíveis para serem atribuídos neste pacote.  Há um pacote Geral que está listado como padrão.  Se você escolher isso acidentalmente, não verá nenhum recurso disponível.

1. Selecione a guia "Funções de recursos"..

1. Selecione os recursos que deseja fornecer em seu pacote de acesso dentre os itens do catálogo catSales. Em seguida, use o menu suspenso **Selecionar função** para definir a função como listada na tabela abaixo.

  | Tipo de recurso | Valor | Função |
  | :---  | :---  | :--- |
  | + Grupos e equipes  | Vendas e Marketing | Membro |
  | + Aplicativos | LinkedIn | msiam_access |
  | + Sites do SharePoint | Vendas nos EUA | Membros de vendas dos EUA |
  | | |

1. Defina o menu suspenso **Selecionar função** para definir a Função como **Membro** para cada item.

1. Selecione **Próximo: Solicitações>** para acessar a guia Solicitações.

1. Em **Usuários que podem solicitar acesso**, selecione **Nenhum (somente atribuições diretas do administrador).

1. Defina **Habilitado** como **Sim**.

1. Vá para a guia **Ciclo de vida** usando os rótulos na parte superior da tela.

1. Escolha os valores para definir o ciclo de vida do pacote:

  | Campo | Valor |
  | :---  | :---  |
  | Expiração de atribuição de pacote de acesso  | Número de dias |
  | As atribuições expiram após | 30 |
  | Os usuários podem solicitar um cronograma específico | Não |
  | Exigir revisões de acesso | Não |
  | | |

1. Selecione **Revisar + Criar** na parte inferior da tela.

1. Revise os valores escolhidos na tela Revisar + Criar.

1. Selecione **Criar** para criar seu pacote de acesso.

#### Tarefa 5: atribuir o pacote a Christopher

1. Verifique se você está em **centro de administração do Microsoft Entra**, **Governança de identidade**, **Gerenciamento de direitos** e se o menu **Pacotes de acesso** está aberto.

1. Selecione **pckSales** que criamos na tarefa anterior.

1. No menu, selecione **Atribuições**.

1. Selecione **+ Nova atribuição** na parte superior da tela.

1. Em **Selecionar política**, use a **Política Inicial** fornecida na lista suspensa.

1. Certifique-se de que **Usuário que já está no meu diretório** esteja marcado.

1. Selecione o item **Adicionar usuários** na caixa de diálogo.

1. Encontre **Christopher Green** na lista de usuários.  Marque a caixa de seleção ao lado do nome dele.  Em seguida, selecione o botão **Selecionar** na parte inferior da tela.

1. Mantenha o restante dos valores com os valores padrões.

1. Selecione o botão **Adicionar** na parte inferior da página.

#### Tarefa 6: verificar se Christopher Green foi adicionado

1. Abra uma **janela do navegador InPrivate**.

1. Acesse o **centro de administração do Microsoft Entra** no endereço `https://entra.microsoft.com`.

1. Faça login no site usando sua conta Chistopher Green e a senha criada anteriormente.

1. Será solicitado que você altere a sua senha.  Defina uma nova senha e grave-a em uma ferramenta como o Bloco de notas para uso futuro.

1. Selecione **Identidade**, **Usuários**, **Todos os usuários** e **Christopher Green**.

1. No menu esquerdo, selecione **Grupos**.

1. Confirme se você recebeu acesso ao grupo **Vendas e Marketing**, de acordo com o pacote de acesso.

1. Selecione **Aplicativos** no menu à esquerda.

1. Confirme se você tem **LinkedIn** em seus aplicativos atribuídos.

#### Tarefa 7: desafio – alterações dinâmicas no pacote de acesso

  **Observação**: esta tarefa não tem instruções passo a passo. O conjunto de tarefas foi fornecido e você pode consultar as etapas anteriores acima para lembrar onde pode fazer alterações específicas.

- Certifique-se de fazer logon no **centro de administração do Microsoft Entra** como sua conta de administrador.
- Abra seu pacote de acesso **pckSales**.
- Vá para as **Funções de recursos** e opte por remover o grupo **Vendas e Marketing** e adicione o grupo **Vendas dos EUA**.
- Use a guia **Atribuições** para **reprocessar** a atribuição.
- Saia e entre novamente como Christopher Green.  Observe que as atribuições em grupo foram alteradas.  Rápido e fácil assim.
- Revogue o acesso excluindo a Atribuição de Christopher Green.

### Conclusão
Este é um laboratório simples para demonstrar os recursos básicos do Gerenciamento de direitos.  Pense na opção para a qual você poderia usar esse recurso e nas opções de configuração avançada que você pode configurar no laboratório.

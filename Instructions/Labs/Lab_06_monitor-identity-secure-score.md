---
lab:
  title: Laboraótio 6 – Monitorar e gerenciar a postura de segurança com a Classificação de segurança de identidade
  module: 'Module : Deploying access using Microsoft Entra entitlement management'
---

# Laboraótio 6 – Monitorar sua postura de segurança gerenciada com a classificação de segurança de identidade

## Cenário do laboratório

O Microsoft Entra Identity Protection fornece detecção e correção automatizadas para riscos baseados em identidade e fornece dados no portal para investigar riscos potenciais. O Microsoft Entra Identity Protection também fornece uma Classificação de Segurança de Identidade para monitorar e melhorar sua postura de segurança de identidade.  Da mesma forma que o Microsoft Defender XDR e o Microsoft Defender para Nuvem, a Classificação de Segurança de Identidade fornece ações de melhoria e recomendações que podem melhorar sua postura de segurança geral para identidade na ID do Microsoft Entra.  Este laboratório vai explorar esta capacidade. 

#### Tempo estimado: 15 minutos

### Exercício 1 – Usando a classificação de segurança de identidade para monitorar e gerenciar a postura de segurança de identidade

#### Tarefa 1 – Analisar a classificação de segurança de identidade e as ações de melhoria

1. Entre no  [https://entra.microsoft.com](https://entra.microsoft.com) como um Administrador global.

2. Abra o menu **Proteção** e selecione **Classificação de Segurança de Identidade**

**OBSERVAÇÃO** – Isso levará você ao painel Classificação de segurança de identidade.

3. Role para baixo para ver as **ações de melhoria**.

4. Ao contrário das ações de melhoria no Microsoft Defender para Nuvem e no Microsoft Defender XDR, essas ações de melhoria são específicas para a identidade.  Isso fornece uma lista mais focada de ações potenciais para o gerenciamento da postura de segurança.  Quaisquer ações de melhoria iniciadas a partir dessa lista também fornecerão um impacto na postura geral de segurança do locatário. 

#### Tarefa 2 – Executar uma ação de melhoria

1. Para melhorar uma área da postura de segurança de identidade, selecione **Habilitar políticas de risco de entrada da Proteção de Identidade do Microsoft Entra ID**.

3. No menu à esquerda, abra **Identity Protection | Política de risco de entrada**.

4. Selecione **Todos os usuários** em **Atribuições**.

5. Selecione **Médio e superior** em **Risco de entrada**.

6. Selecione **Permitir** - **Exigir autenticação multifator**, em **Controles**.

7. Transforme a **imposição de política** para **Habilitada** (se ainda não tiver sido feita) e selecione **Salvar**.

8. Você criou uma política de risco de entrada que agora deve aumentar sua classificação de segurança de identidade.  Isso levará até 24 horas para entrar em vigor na sua classificação de segurança de identidade.

9. Revise outras ações de melhoria e as etapas para criá-las e habilitá-las.

# Projeto Lava-Rápido — Escopo e Diretrizes

**Status:** Proposta para validação
**Tipo:** Projeto educacional
**Prazo estimado:** 1 a 2 semanas

## 1. Objetivo do projeto

&#x20;projeto consiste no desenvolvimento de um sistema de gerenciamento de lava-rápido em C#, executado em console, utilizando Entity Framework Core com abordagem Code First e SQL Server para persistência de dados.

Seu objetivo principal é consolidar conhecimentos de Programação Orientada a Objetos, modelagem de domínio, regras de negócio, persistência de dados e separação de responsabilidades, por meio da implementação de um fluxo operacional simplificado.

O sistema abrangerá o gerenciamento de usuários, autenticação básica, agendamentos, controle de disponibilidade, execução de atendimentos e consultas operacionais simples.

A implementação deverá priorizar código organizado, responsabilidades bem definidas e boas práticas proporcionais à complexidade do projeto. Padrões de projeto e recursos arquiteturais serão adotados quando houver benefício concreto para a compreensão, manutenção ou evolução do código.

O escopo será limitado a uma aplicação local, de pequeno porte, utilizada por um usuário por vez e sem interface gráfica. O desenvolvimento deverá ser concluído preferencialmente em uma a duas semanas.

Funcionalidades, abstrações e tecnologias adicionais somente serão incorporadas quando contribuírem significativamente para os objetivos educacionais, sem comprometer o prazo ou ampliar desnecessariamente a complexidade do projeto.

## 2. Diretrizes gerais

- **Linguagem:** C#.
- **Interface:** aplicação de console.
- **Persistência:** SQL Server.
- **ORM:** Entity Framework Core.
- **Abordagem de modelagem e banco:** Code First.
- **Arquitetura:** separação de responsabilidades em camadas, proporcional à complexidade do projeto.
- **Prazo:** uma a duas semanas de desenvolvimento.
- **Ambiente de execução:** aplicação local, em uma única máquina, utilizada por uma pessoa por vez.

A implementação deverá priorizar clareza, simplicidade e boas práticas de programação. Padrões de projeto e recursos arquiteturais serão adotados quando trouxerem benefícios concretos para a organização, compreensão ou manutenção do código.

Não deverão ser introduzidas abstrações, tecnologias ou funcionalidades apenas por serem consideradas boas práticas em projetos maiores.

## 3. Objetivos educacionais

O desenvolvimento deverá contribuir principalmente para:

1. Aplicar POO na organização e no comportamento dos objetos.
2. Praticar encapsulamento, responsabilidades e regras de negócio.
3. Modelar e persistir dados relacionais utilizando EF Core e SQL Server.
4. Trabalhar com relacionamentos, consultas, filtros e agregações.
5. Utilizar Code First e o gerenciamento de alterações do esquema do banco.
6. Separar responsabilidades entre interface, lógica de negócio e acesso a dados.
7. Integrar autenticação já implementada à persistência de dados.
8. Aplicar padrões e boas práticas quando houver justificativa técnica.

## 4. Escopo funcional

### 4.1. Gerenciamento de usuários

- Cadastrar usuários.
- Consultar usuários.
- Atualizar dados cadastrais.
- Inativar usuários.
- Diferenciar clientes e administradores.

### 4.2. Autenticação e controle de acesso

- Realizar login e encerramento de sessão.
- Identificar o usuário autenticado e seu perfil.
- Restringir funcionalidades conforme o perfil.
- Adaptar o código de autenticação existente para utilizar dados persistidos.

A autenticação faz parte do escopo principal. A implementação deverá aproveitar a lógica já desenvolvida, evitando reconstruções desnecessárias.

### 4.3. Gerenciamento de agendamentos

- Registrar agendamentos.
- Consultar agendamentos.
- Cancelar agendamentos.
- Verificar disponibilidade.
- Impedir conflitos de horário dentro das condições de funcionamento definidas para a aplicação.

### 4.4. Gerenciamento de atendimentos

- Identificar agendamentos elegíveis para atendimento.
- Registrar a realização de um atendimento.
- Consultar atendimentos realizados.

### 4.5. Histórico do cliente

O cliente deverá poder consultar seus próprios registros de:

- Agendamentos.
- Atendimentos realizados.

O acesso ao histórico deverá respeitar a identidade do usuário autenticado, sem permitir que um cliente consulte os registros particulares de outro.

### 4.6. Consultas administrativas

O administrador deverá poder consultar:

- Total de agendamentos no período definido.
- Total de atendimentos no período definido.

Os resultados deverão ser apresentados em formato textual no console, sem necessidade de gráficos ou ferramentas externas de análise.

### 4.7 Janela temporl
- A janela temporal para novos agendamentos deve ser de 7 dias, o dia atual (hoje) + 6 dias.
- A janela temporal para proximos agendamentos realizados pelos clientes deve ser de 7 dias, semanal de domingo a sabado, podendo nagevar para as proximas semanas.
- A janela temporal para proximos agendamentos a serem realizados pelo adiministrador deve ser de 7 dias, semanal de domingo a sabado, podendo nagevar para as proximas semanas.
- A janela temporal dos agendamentos/atendimentos do cliente (passado) deve ser de 7 dias, semanal de domingo a sabado, podendo nagevar para as semanas anteriores.
- A janela temporal dos agendamentos/atendimentos realizados pelo adimistrador (passado) deve ser de 7 dias, semanal de domingo a sabado, podendo nagevar para as semanas anteriores.
- A janela temporal dos relatórioes devem ser de 7 dias, semanal de domingo a sabado, podendo navegar para as proximas semanas ou para as semanas anteriores.

## 5. Limites técnicos e operacionais

O sistema será executado localmente, em uma única instância e com um usuário por vez.

Por esse motivo, não fazem parte dos requisitos:

- Suporte a múltiplas instâncias concorrentes.
- Infraestrutura distribuída.
- Sincronização entre dispositivos.
- Mecanismos avançados de concorrência distribuída.

Essa simplificação não elimina a necessidade de validar a disponibilidade dos horários nem de impedir conflitos entre agendamentos registrados.

A aplicação deverá manter seus dados após o encerramento e a reabertura do programa, utilizando o SQL Server como mecanismo de persistência.

## 6. Funcionalidades fora do escopo

Não serão implementados, nesta versão:

- Pagamentos, caixa ou controle financeiro.
- Controle de estoque e compras.
- Emissão de notas fiscais.
- Integrações com WhatsApp, e-mail ou serviços externos.
- Interfaces web ou mobile.
- Aplicação desktop com interface gráfica.
- Gestão de múltiplas unidades ou filiais.
- Relatórios financeiros, gráficos ou ferramentas de BI.
- Arquitetura distribuída ou microsserviços.
- Infraestrutura avançada de segurança ou autenticação.
- Funcionalidades operacionais que não contribuam diretamente para os objetivos educacionais.

A exclusão desses itens não significa que sejam desnecessários em um produto comercial, mas que seu custo não se justifica neste exercício.

## 7. Critérios para inclusão de funcionalidades

Novas funcionalidades deverão ser avaliadas considerando os seguintes critérios.

### 7.1. Benefício educacional

A funcionalidade deverá contribuir de maneira identificável para o aprendizado de C#, POO, EF Core, SQL Server, regras de negócio ou organização do código.

### 7.2. Relação com o objetivo

Deverá apoiar diretamente o fluxo de usuários, agendamentos, atendimentos ou consultas previstas no escopo.

### 7.3. Custo de implementação

O benefício esperado deverá justificar o tempo necessário para implementação, depuração e validação.

### 7.4. Compatibilidade com o prazo

A inclusão não deverá comprometer a conclusão do núcleo funcional dentro do prazo de uma a duas semanas.

### 7.5. Simplicidade

Quando duas soluções atenderem adequadamente ao requisito, deverá ser preferida a alternativa mais simples, clara e proporcional ao problema.

### 7.6. Necessidade de abstrações e padrões

Interfaces, padrões de projeto e camadas adicionais deverão ser adotados quando houver uma justificativa concreta, e não apenas para reproduzir arquiteturas de sistemas maiores.

## 8. Critérios para exclusão de funcionalidades

Uma funcionalidade deverá ser excluída ou adiada quando:

- Não contribuir significativamente para os objetivos educacionais.
- Introduzir complexidade desproporcional ao benefício.
- Exigir tecnologias ou integrações que desviem o foco do projeto.
- Duplicar capacidades já atendidas por uma solução mais simples.
- Não ser necessária para completar o fluxo principal.
- Comprometer o prazo estabelecido.

## 9. Critérios de conclusão

O projeto poderá ser considerado concluído quando:

- O sistema permitir cadastrar, consultar, atualizar e inativar usuários.
- O login existente estiver integrado à persistência.
- Os perfis de cliente e administrador tiverem acesso compatível com suas responsabilidades.
- Os agendamentos puderem ser registrados, consultados e cancelados.
- A disponibilidade dos horários for validada.
- Os atendimentos puderem ser registrados e consultados.
- O cliente puder consultar seu próprio histórico.
- O administrador puder consultar os indicadores definidos para o período de sete dias.
- Os dados persistirem corretamente no SQL Server.
- O código estiver organizado de maneira coerente com as diretrizes.
- O fluxo principal tiver sido validado por testes ou verificações práticas.

A implementação de funcionalidades fora do escopo não será necessária para considerar o projeto concluído.

## 10. Registro de decisões

| ID      | Decisão                                                  | Situação                                         |
| ------- | -------------------------------------------------------- | ------------------------------------------------ |
| ESC-001 | Aplicação de console em C#                               | Definida                                         |
| ESC-002 | EF Core, Code First e SQL Server                         | Definida                                         |
| ESC-003 | Projeto educacional de pequeno porte                     | Definida                                         |
| ESC-004 | Prazo-alvo de uma a duas semanas                         | Definida                                         |
| ESC-005 | POO aplicada e regras de negócio como foco               | Definida                                         |
| ESC-006 | Login simples reaproveitando código existente            | Definida                                         |
| ESC-007 | Controle de disponibilidade e conflitos                  | Definida                                         |
| ESC-008 | Histórico do cliente e consultas administrativas         | Definida                                         |
| ESC-009 | Execução local, com um usuário por vez                   | Definida                                         |
| ESC-010 | Avaliação de novas funcionalidades por benefício e custo | Definida                                         |
| ESC-011 | Janela base de 7 dias, variando conforme o item 4.7      | Definida                                         |
| ESC-012 | O ciclo de desenvolvimento deve ter de 8 a 15 etapas     | Definida                                         |

### Manutenção das decisões

As decisões registradas deverão orientar as próximas etapas do desenvolvimento.

Sugestões não serão consideradas decisões aprovadas até serem validadas. Alterações posteriores deverão ser justificadas e avaliadas quanto ao impacto no escopo, na complexidade e no prazo.

Este documento delimita o projeto em nível geral. A modelagem das entidades, os relacionamentos, as regras de negócio detalhadas e as decisões de implementação serão definidos em etapas posteriores.

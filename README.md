# Sistema de Gerenciamento de Oficina Mecânica

Este repositório contém o esquema conceitual para um sistema de controle e execução de ordens de serviço (OS) em uma oficina mecânica, desenvolvido como parte de um desafio de projeto.

## 📝 Descrição do Contexto
O sistema visa gerenciar o fluxo desde a entrada do veículo pelo cliente até a execução final do serviço pela equipe de mecânicos.

### Fluxo Principal:
1.  **Clientes e Veículos:** Clientes trazem veículos para conserto ou revisão. Um cliente pode possuir vários veículos.
2.  **Equipes e Mecânicos:** Cada veículo é atendido por uma **Equipe de Mecânicos**. A equipe é composta por vários profissionais com diferentes especialidades.
3.  **Ordem de Serviço (OS):** A equipe identifica os problemas e gera uma OS contendo número, datas (emissão e conclusão), valor total e status.
4.  **Cálculo de Valores:**
    * **Serviços:** Baseados em uma tabela de referência de mão-de-obra.
    * **Peças:** O valor das peças utilizadas é somado ao valor da mão-de-obra para compor o total da OS.
5.  **Autorização:** O serviço só é executado após a autorização do cliente.

## 🗄️ Estrutura do Esquema (Entidades e Atributos)

- **Cliente:** idCliente, Nome, CPF/CNPJ, Contato.
- **Veiculo:** idVeiculo, Placa, Marca, Modelo, idCliente (FK).
- **Equipe:** idEquipe, NomeEquipe.
- **Mecanico:** idMecanico, Nome, Endereço, Especialidade, idEquipe (FK).
- **Ordem de Serviço (OS):** idOS, DataEmissao, DataConclusao, ValorTotal, Status, idVeiculo (FK), idEquipe (FK).
- **Serviço:** idServico, Descricao, ValorMaoDeObra.
- **Peça:** idPeca, Descricao, ValorUnitario.
- **Tabelas Associativas (N:M):** `OS_Servicos` e `OS_Pecas` para gerenciar quais itens compõem cada ordem de serviço específica.

## 🚀 Como visualizar
O arquivo `.drawio` pode ser aberto no [diagrams.net](https://app.diagrams.net/).

---
Desenvolvido por Geremias Santos Bezerra

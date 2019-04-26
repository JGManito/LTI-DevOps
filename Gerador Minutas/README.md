#Gerador de Minutas

Este programa serve para gerar minutas e orçamentos em PDF. 

Este programa é para ser desenvolvido em Python 3, podendo usar quaisquer bibliotecas, mas estas devem ser mantidas ao mínimo possível para diminuir entropia nas dependências. O código deve usar extensivamente comentários, e a criação de funções especializadas ("black boxes") é altamente aconselhada.

O desenvolvimento do mesmo está dividido nas seguintes fases:

- [ ] Proof of concept - Termo de responsabilidade de empréstimos (Desnecessária interface gráfica, basta CLI)
      - [ ] Recebe do utilizador os seguintes campos:
            - Nome do colaborador
            - Material a ser emprestado
            - Nome, número de aluno e contacto da pessoa que requisitou o material
            - Data e hora de levantamento (perguntando se quer usar a data/hora do sistema)
            - Data e hora prevista para entrega
      - [ ] Gera campos para preencher após impressão para:
            - Dia e hora de entrega
            - Colaborador a quem foi entregue o material
            - Assinatura
      - [ ] Imprime no ficheiro o texto do termo de responsabilidade
      - [ ] Gerar um PDF simples para testar o funcionamento correcto do mesmo
      
- [ ] Fase 1 - Gerador de orçamentos (Desnecessária interface gráfica, basta CLI)
      - [ ] Recebe do utilizador os seguintes dados:
            - Número de orçamento
            - Data do orçamento
            - Nome do Colaborador
            - Nome Cliente
            - Morada1 Cliente
            - Morada2 Cliente (fazer check se existe. Caso não exista/esteja em branco, garantir que não deixa um espaço em branco no orçamento)
            - Código Postal Cliente
            - NIF Cliente
      - [ ] Recebe um ficheiro JSON com os seguintes dados:
            - Artigo
            - Quantidade
            - Preço unitário
      - [ ] Gera uma tabela com os items do ponto anterior
      - [ ] Gera um PDF simples para testar o funcionamento correcto do mesmo
      - [ ] Gera um PDF devidamente formatado com o orçamento
      
- [ ] Fase 2 - Criação de uma interface gráfica
      - [ ] Criar um menu que pergunte o tipo de minuta pretendida
      - [ ] Criar campos para cada uma das informaçoes pedidas anteriormente (o ficheiro JSON fica de fora, pode continuar a ser)
      - [ ] Criar um botão para poder escolher o ficheiro JSON a ler
      - [ ] A interface tem de ter um campo que permita ver uma tabela com o conteúdo (parsed) do ficheiro JSON

- [ ] Fase 3 - Criar possibilidade de editar todos os campos dos documentos
      - [ ] Alterar todos os campos que possam necessitar de ser editados para variáveis
      - [ ] Criar um botão de override na GUI de cada minuta que abra uma nova janela com os campos anteriores mais os outros campos relevantes para cada tipo de documento
      
- [ ] Fase 4 - Possibilitar input de todos os campos do orçamento a partir de um ficheiro JSON
      - [ ] Criar um programa que gera um ficheiro JSON usando dados artificiais semelhantes aos presentes num GID
      - [ ] Criar uma rotina que consiga converter todos estes dados em variáveis que possam ser usadas pelo programa
      - [ ] Alterar o comportamento do botão que importa o ficheiro JSON para importar o ficheiro com todos os dados do GID para o programa
      - [ ] Garantir que os dados são mostrados na GUI antes de gerar o PDF, inclusivamente a tabela de artigos/quantidades/preços

- [ ] Fase 5 - Integração com o jobs
      - [ ] Criar uma rotina no jobs que exporte o conteúdo do GID para um ficheiro JSON, faltando apenas os dados do colaborador, da data e o número do orçamento
      - [ ] Alterar a base de dados para incluir o número de orçamento e gerar automáticamente o ficheiro JSON
      - [ ] Meter o programa no backend do LTI e integrar numa página web

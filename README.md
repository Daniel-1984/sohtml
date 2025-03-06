Documentação do Sistema de Pesquisa de Refrigerante
Visão Geral
Este documento descreve o sistema de pesquisa interativo sobre consumo de refrigerante desenvolvido como uma aplicação web em HTML, CSS e JavaScript. A aplicação permite coletar dados sobre o comportamento das pessoas quanto ao consumo de refrigerante, registrar essas informações e apresentar estatísticas sobre o volume total consumido.
Objetivo
O sistema visa coletar e analisar padrões de comportamento relacionados ao consumo de refrigerante, especialmente focando na indecisão entre consumir ou não, através de três níveis de resposta: consumo total, consumo parcial (golinho ou tiquinho) ou nenhum consumo.
Tecnologias Utilizadas

HTML5
CSS3
JavaScript (ES6+)
Design responsivo

Estrutura do Sistema
1. Interface de Usuário
A interface do sistema é dividida em três áreas principais:

Área de Entrada de Dados: Campo para nome do participante e indicador do total de pessoas
Área de Perguntas e Resultados: Exibe perguntas sequenciais e o resultado final
Área de Histórico e Estatísticas: Mostra dados acumulados de todos os participantes

2. Fluxo de Interação
O sistema implementa um fluxo de perguntas condicionais:

Pergunta inicial: "Vai tomar refrigerante?"

Se "Sim" → Registra consumo total (300ml)
Se "Não" → Avança para a segunda pergunta


Segunda pergunta: "Mas nem um golinho?"

Se "Sim" → Registra consumo parcial (150ml)
Se "Não" → Avança para a terceira pergunta


Terceira pergunta: "E um tiquinho, só para experimentar?"

Se "Sim" → Registra consumo mínimo (75ml)
Se "Não" → Registra nenhum consumo (0ml)



3. Sistema de Armazenamento
Os dados são armazenados temporariamente (durante a sessão do navegador) em:

Array historicoRespostas - Guarda todas as respostas individuais
Variáveis para contadores (totalSim, totalGolinho, totalTiquinho, totalNao)
Variável volumeTotal para o volume acumulado de refrigerante

4. Cálculo de Volume
O sistema define volumes fixos para cada nível de consumo:

Copo inteiro: 300ml
Golinho: 150ml (50% do copo)
Tiquinho: 75ml (25% do copo)
Recusa: 0ml

5. Visualização de Dados
As estatísticas são apresentadas de várias formas:

Contadores numéricos para cada tipo de resposta
Volume total em ml e convertido para litros
Barra de progresso visual mostrando o avanço em direção à meta de 5 litros
Tabela de histórico com todas as respostas individuais

Componentes Técnicos
1. Funções Principais

atualizarNome(): Atualiza o nome do participante nos elementos da interface
responder(pergunta, resposta): Processa a resposta do usuário e avança no fluxo
mostrarResultado(emoji, mensagem): Exibe o resultado da decisão e atualiza estatísticas
atualizarHistorico(): Atualiza a tabela com o histórico de todas as respostas
atualizarEstatisticas(): Recalcula e atualiza todos os contadores e a barra de progresso
novaPessoa(): Reinicia o fluxo para um novo participante


Possíveis Melhorias Futuras

Implementação de persistência de dados usando localStorage ou backend
Exportação dos resultados em formato CSV ou PDF
Adição de visualizações mais sofisticadas como gráficos
Personalização dos volumes de cada tipo de resposta
Implementação de autenticação para múltiplos administradores


![image](https://github.com/user-attachments/assets/0a813a97-64a1-482c-bf39-2f9661c2c724)


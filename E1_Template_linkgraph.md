# E1 — Proposta e Definição do Projeto

> **Disciplina:** Teoria dos Grafos  
> **Prazo:** 16 de março de 2026  
> **Peso:** 10% da nota final  

---

## Identificação do Grupo

| Campo | Preenchimento |
|-------|---------------|
| Nome do projeto |linkgraph |
| Integrante 1 | julia emily leonardo barbosa — 39325041 |
| Domínio de aplicação | ex.: rede social profissional|

---

## 1. Contexto e Motivação

> Descreva o problema do mundo real que será abordado. Por que ele é relevante?  
> *Orientação: 2 a 3 parágrafos. Seja específico — evite generalizações.*

<!-- O projeto LinkGraph surge como uma resposta estratégica à crescente complexidade das redes de networking profissional contemporâneas. Em plataformas massivas como o LinkedIn, a saturação de informações e o volume excessivo de conexões superficiais muitas vezes ocultam o que realmente importa: o caminho mais curto e eficiente para alcançar mentores, especialistas ou parceiros de negócios. Para estudantes e profissionais em início de carreira, essa "poluição visual" de dados torna difícil identificar quem são as figuras centrais em nichos específicos, como Odontologia ou Tecnologia, dificultando a criação de laços que realmente impulsionem o desenvolvimento profissional.

A relevância deste problema reside na necessidade de transformar dados brutos em inteligência logística de carreira. Ao modelar uma rede social através da Teoria dos Grafos — tratando indivíduos como vértices e suas interações como arestas — deixamos de ver apenas uma lista de nomes e passamos a visualizar uma estrutura matemática navegável. Isso permite que algoritmos identifiquem "pontes" entre comunidades distintas e sugiram conexões que não seriam óbvias à primeira vista, otimizando o capital social dos usuários através de análise estrutural.-->

---

## 2. Objetivo Geral

> O que o sistema deve ser capaz de fazer ao final?  
> *Orientação: 1 frase clara e objetiva. Ex.: "O sistema deve calcular a rota de menor custo entre dois pontos em um mapa urbano."*

<!-- Desenvolver um sistema computacional capaz de carregar, processar e analisar uma rede social profissional, identificando conexões inteligentes e sugerindo interações baseadas na profundidade e estrutura da rede. -->

---

## 3. Objetivos Específicos

> Desmembre o objetivo geral em metas mensuráveis.  
> *Orientação: liste entre 3 e 5 itens. Cada item deve ser verificável — use verbos como "implementar", "calcular", "exibir", "carregar".*

- [ implementar um módulo de infraestrutura para leitura e carga de dados de usuários e conexões a partir de arquivos no formato JSON.] 
- [ Implementar o algoritmo de Dijkstra para calcular de forma precisa o grau de separação (caminho mínimo) entre dois usuários quaisquer na rede.] 
- [ Desenvolver um gerador de grafos aleatórios parametrizável para validar o desempenho e a escalabilidade do sistema com até 10.000 vértices. ] 
- [ Criar uma interface de linha de comando (CLI) que permita ao usuário consultar sugestões de conexões e visualizar caminhos de networking. ] 

---

## 4. Público-Alvo / Caso de Uso Principal

> Para quem ou em qual cenário o sistema seria utilizado?  
> *Orientação: descreva um cenário concreto de uso. Ex.: "Um entregador de aplicativo que precisa otimizar a sequência de entregas em um bairro."*

<!-- O sistema foi idealizado para estudantes universitários e profissionais em transição de carreira que precisam mapear o mercado de trabalho de forma técnica. Um cenário concreto de uso seria o de um estudante de graduação que deseja ingressar em uma área específica de especialização. Através do LinkGraph, ele poderia visualizar não apenas quem trabalha naquela área, mas qual é o "grau de separação" entre ele e um coordenador de RH de uma grande empresa. O sistema atuaria como um GPS de networking, indicando, por exemplo: "Você não conhece a pessoa X, mas possui três conexões em comum que podem servir como ponte para uma apresentação formal". -->

---

## 5. Justificativa Técnica — Por que Grafos?

> Por que a modelagem em grafo é a abordagem mais adequada para este problema?  
> *Orientação: explique quais elementos do problema mapeiam naturalmente para vértices e arestas. Mencione se há pesos, direção, ou restrições que reforçam a escolha.*

<!-- A modelagem em grafo é a abordagem mais adequada porque as relações humanas são inerentemente redes, não tabelas estáticas. Diferente de bancos de dados relacionais tradicionais (SQL), onde descobrir conexões de terceiro ou quarto nível exigiria múltiplos "joins" custosos que degradam a performance, a Teoria dos Grafos utiliza estruturas otimizadas como a Lista de Adjacência. Esta representação é ideal para redes sociais, que são tipicamente "esparsas" (onde cada usuário conhece apenas uma fração minúscula do total de pessoas), permitindo economizar memória e processar buscas em milissegundos.

Além disso, a aplicação do algoritmo de Dijkstra permite que o sistema não apenas encontre qualquer caminho, mas o caminho de menor custo, considerando "pesos" nas arestas que podem representar a força do vínculo ou a afinidade entre os profissionais. O uso de defaultdict(list) na implementação em Python garante que o sistema seja resiliente a erros de inserção e capaz de escalar dinamicamente conforme novos usuários (vértices) e interações (arestas) são adicionados à plataforma, mantendo a integridade da topologia da rede. -->

---

## 6. Tipo de Grafo

> Especifique as características do grafo que o problema requer.

| Característica | Escolha | Justificativa breve |
|----------------|---------|---------------------|
| Dirigido ou não-dirigido | | nao dirigido | Se duas pessoas possuem um vínculo profissional, a conexão é mútua (ambos são vizinhos).

| Ponderado ou não-ponderado | | ponderado | O peso pode representar o nível de interação ou afinidade entre os usuários.

| Conectado / bipartido / geral | | geral | O grafo pode ser desconexo (usuários novos sem amigos) e conter ciclos complexos.

| Representação interna pretendida | lista de adjacência / matriz       |lista de adjacencia | Mais eficiente para percorrer vizinhos em redes esparsas e economizar memória.

---

## 7. Diagrama Conceitual

> Insira aqui ao menos uma figura que ilustre o domínio do problema.  
> *Pode ser uma imagem exportada do Draw.io, Excalidraw, foto de esboço à mão etc.*  

<!--  O diagrama ilustra a rede profissional LinkGraph centrada no usuário ('voce'). As arestas não-dirigidas representam conexões mútuas, enquanto os pesos indicam a 'distância' ou 'custo' da interação (ex.: frequência de contato ou afinidade), base para o cálculo de caminhos mínimos pelo algoritmo de Dijkstra  -->

**Legenda:** 

---

## Checklist de Entrega

Antes de submeter, confirme:

- [ x ] Texto entre 300 e 600 palavras (seções 1 a 5)
- [ x ] Todos os campos da tabela de identificação preenchidos
- [ x ] Tipo de grafo especificado com justificativa
- [ x ] Diagrama presente e referenciado no texto
- [ x ] Arquivo nomeado como `E1_NomeGrupo_Grafos.docx` (versão Word) ou PR aberto (versão GitHub)

---

*Teoria dos Grafos — Profa. Dra. Andréa Ono Sakai*

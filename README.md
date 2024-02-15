## Análise de Texto com o Serviço de Linguagem

desafio [dio.me](dio.me)

1. Crie uma pasta chamada 'inputs' e crie um documento de texto com algumas sentenças
2. Crie um arquivo chamado readme.md , deixe alguns prints descreva o processo, alguns insights e possibilidades que você aprendeu durante o conteúdo após a IA analisar suas sentenças



*decidi através da documentação criar um resumo no readme sobre [Conceitos básicos da Análise de Texto com o Serviço de Linguagem](https://learn.microsoft.com/pt-br/training/modules/analyze-text-with-text-analytics-service/)*



## Entenda o Text Analytics

Antes de explorar os recursos de análise de texto do serviço Azure AI Language, vamos examinar alguns princípios gerais e técnicas comuns usadas para executar análise de texto e outras tarefas de processamento de linguagem natural (NLP).

Algumas das primeiras técnicas usadas para analisar texto com computadores envolvem análise estatística de um corpo de texto (a corpus) para inferir algum tipo de significado semântico. Simplificando, se você pode determinar as palavras mais comumente usadas em um determinado documento, muitas vezes você pode ter uma boa idéia do que é o documento.

## Tokenização

O primeiro passo para analisar um corpus é dividi-lo em tokens. Por uma questão de simplicidade, você pode pensar em cada palavra distinta no texto de treinamento como um token, embora, na realidade, os tokens possam ser gerados para palavras parciais, ou combinações de palavras e pontuação.

Por exemplo, considere esta frase de um famoso discurso presidencial dos EUA: "escolhemos ir à Lua". A frase pode ser dividida nos seguintes tokens, com identificadores numéricos:

.nós

.escolher

.para

.ir

.o

.lua

Observe que "to" (token número 3) é usado duas vezes no corpus. A frase "escolhemos ir à Lua" pode ser representado pelos tokens [1,2,3,4,3,5,6].


Usamos um exemplo simples no qual os tokens são identificados para cada palavra distinta no texto. No entanto, considere os seguintes conceitos que podem ser aplicados à tokenização, dependendo do tipo específico de problema de PNL que você está tentando resolver:


Normalização de texto: Antes de gerar tokens, você pode optar por normalizar o texto removendo a pontuação e alterando todas as palavras para minúsculas. Para uma análise que se baseia puramente na frequência de palavras, essa abordagem melhora o desempenho geral. No entanto, algum significado semântico pode ser perdido - por exemplo, considere a frase "Banks trabalhou em muitos bancos.". Você pode querer que sua análise diferencie entre a pessoa Sr. Banks e o bancos em que trabalhou. Você também pode querer considerar "bancos." como um token separado para "bancos" porque a inclusão de um período fornece a informação de que a palavra vem no final de uma frase

Parar a remoção de palavras. Stop words são palavras que devem ser excluídas da análise. Por exemplo, "o", "a", ou "é" faça o texto mais fácil para as pessoas lerem, mas adicione pouco significado semântico. Ao excluir essas palavras, uma solução de análise de texto pode ser mais capaz de identificar as palavras importantes.

n-gramas são frases de vários termos, como "Eu tenho" ou "ele andou". Uma única palavra é uma unigrama, uma frase de duas palavras é uma bi-grama, uma frase de três palavras é uma tri-grama, e assim por diante. Ao considerar as palavras como grupos, um modelo de aprendizado de máquina pode entender melhor o texto.

Despertar é uma técnica na qual algoritmos são aplicados para consolidar palavras antes de contá-las, de modo que palavras com a mesma raiz, como "poder", "poder" e "poder", são interpretados como sendo o mesmo símbolo.

## Análise de frequência

Depois de tokenizar as palavras, você pode realizar alguma análise para contar o número de ocorrências de cada token. As palavras mais usadas (exceto pare as palavras como "a", "o", e assim por diante) muitas vezes pode fornecer uma pista sobre o assunto principal de um corpus de texto. Por exemplo, as palavras mais comuns em todo o texto do discurso "ir para a lua" que consideramos anteriormente incluem "novo", "ir", "espaço", e "lua". Se fôssemos tokenizar o texto como bi-gramas (pares de palavras), o bi-grama mais comum no discurso é "a lua". A partir dessas informações, podemos facilmente supor que o texto está preocupado principalmente com viagens espaciais e indo para a lua.

## Aprendizado de máquina para classificação de texto

Outra técnica de análise de texto útil é usar um algoritmo de classificação, como regressão logística, para treinar um modelo de aprendizado de máquina que classifica o texto com base em um conjunto conhecido de categorizações. Uma aplicação comum desta técnica é treinar um modelo que classifica o texto como positivo ou negativo para executar análise de sentimentos ou mineração de opinião.

Por exemplo, considere as seguintes avaliações de restaurantes, que já estão rotuladas como 0 (negativo) ou 1 (positivo):

.A comida e o serviço foram ambos excelentes: 1

.Uma experiência realmente terrível: 0

.Mmm! comida saborosa e uma vibe divertida: 1

.Serviço lento e comida abaixo do padrão: 0

Com avaliações rotuladas suficientes, você pode treinar um modelo de classificação usando o texto tokenizado como características e o sentimento (0 ou 1) a etiqueta. O modelo encapsulará uma relação entre tokens e sentimento - por exemplo, revisões com tokens para palavras como "ótimo", "saboroso", ou "divertido" é mais provável que retorne um sentimento de 1 (positivo), enquanto comentários com palavras como "terrível", "lento", e "abaixo do padrão" é mais provável que retornem 0 (negativo).


## Modelos de linguagem semântica

À medida que o estado da arte da PNL avançou, a capacidade de treinar modelos que encapsulam a relação semântica entre tokens levou ao surgimento de poderosos modelos de linguagem. No coração desses modelos está a codificação de tokens de linguagem como vetores (matrizes multivaloradas de números) conhecidas como incorporações.

Pode ser útil pensar nos elementos em um vetor de incorporação de token como coordenadas no espaço multidimensional, de modo que cada token ocupe um "local" específico." Quanto mais próximos os tokens estiverem um do outro ao longo de uma dimensão particular, mais semanticamente relacionados eles estarão.

## Tarefas comuns de PNL suportadas por modelos de linguagem incluem:

Análise de texto, como extrair termos-chave ou identificar entidades nomeadas no texto.

Análise de sentimentos e mineração de opinião para categorizar o texto como positivo ou negativo.

Tradução automática, em que o texto é traduzido automaticamente de um idioma para outro.

Summarização, em que os principais pontos de um grande corpo de texto são resumidos.

Soluções de IA conversacionais, como bots ou assistentes digitais em que o modelo de linguagem pode interpretar a entrada de linguagem natural e retornar uma resposta apropriada.




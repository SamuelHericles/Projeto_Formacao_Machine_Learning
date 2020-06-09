# Projeto_Formacao_Machine_Learning

Caso queria executar esse notebook no seu computador, se o sistema operacional for windows, apenas execute o arquivo **StartJupyter** 
e espere uma aba abrir no seu navegador.Caso seja de distribuição Linux, rode o comando ```jupyer-notebook``` no diretório local de download deste projeto no seu computador.

## Situação problema

Você foi contratado por uma empresa a explorar informações sobre o ENEM e verificar a possibilidade de oferecer bolsas de estudos para os alunos e alunas que tiram as melhores notas, mesmo que não façam todas as provas. Será possível prever as melhores notas ou os melhores alunos sem que eles façam todas as provas?
  
Nesse seu primeiro trabalho de Machine Learning você vai usar regressões e classificações para resolver o problema da empresa, além de cross validation e muito mais.

Para isso você deve acessar o projeto e o conjunto de dados disponíveis em https://github.com/alura-cursos/formacao-machine-learning. Lá você encontra o jupyter notebook para que você possa trabalhar e o link para a fonte de dados do governo.

## Modelos utilizados
  * Estimadores
  1. ```LinearRegression()```
  2. ```Lasso() ```
  3. ```Ridge() ```
  4. ```DecisionTreeRegressor() ```
  5. ```RandomForestRegressor()```
  
  * Classificadores
  1. ```DummyClassifier()```
  2. ```LogisticRegression()``` 
  3. ```RidgeClassifier()``` 
  4. ```DecisionTreeClassifier()``` 
  5. ```RandomForestClassifier()``` 
  6. ```SVC()```


## Alguns pontos sobre o projeto
  * Nos modelos de previsão a ideia era tentar estimar as notas faltantes do alunos(as) e nos modelos de classificação foi para diferenciar quais os alunos que estariam melhores classificados.
  * Os microdados enem 2017, possui mais de 6 milhões de linhas, logo não consegui carregar todas. Com isso, o material utilizado foi com apenas 1 milhão de linhas das quais foram removidas as que não possuiam nenhuma de nota.
  * É muito interessante ver que as notas dos alunos e alunas se comportam bem como uma gaussiana. No código foi utilizado a função ```distplot()``` do seaborn com a coluna 'nota_total' que a soma de todas as nove competetências que o enem analisa.
  * Fiz uma simples heurística com apenas as notas de linguagens e código e ciências humanas para classificar os alunos que poderiam está no top 25% caso fizessem todas as provas.A ideia foi que um aluno ou aluna participasse apenas do primeiro dia e não tinha nenhuma idea de redigir algo com o tema proposto. Obtive acurácia de 77% que é maior que o baseline usando ```DummyClassifier()``` do sklearn.
  * Como as notas possuem uma correlação linear com a nota_total, podemos aplicar modelos de previsão como regressão linear ou logistica e facilmente pode prever as notas faltantes dos alunos e alunas. Porém, o desafio seria se poderiamos prever as notas entre as competências(a nota de linguagens e código podia prever a nota da redação do aluno(as), por exemplo).

# Previsão do uso de leitos de UTI por pacientes com Covid-19

<p align="center">
  <img src="https://github.com/EltonGS/covid-19_previsao_leito_UTI/blob/main/Imagens/uti.jpg">
</p>

# Sumário

1. [Apresentação](#apresent)
2. [Introdução](#intro)
3. [Estrutura do Projeto](#estrutura)
4. [Informações sobre os dados](#dados)
5. [Objetivos](#goals)
6. [Conclusão](#conclusao)
7. [Agradecimentos](#thanks)
8. [Referências utilizadas](#refer)

<a name=apresent></a>
## Apresentação

Olá a todos!

Seja bem vindo a esse projeto de Ciência de Dados. Contando um pouco sobre mim e o que me levou a conhecer e me interessar por essa área:

Em meados de março de 2021 a empresa onde trabalho disponibilizou uma série de cursos para que os funcionários estivessem cientes das tecnologias e temas que são extremamente importantes para o crescimentos dos clientes. Um desses cursos era sobre Dados e como eles são utilizados para impulsionar o crescimento de empresas, as tomadas de decisões, e como a utilização de dados vem aumentando e ainda há muito a ser explorado.

A maneira como os dados podem ser utilizados para extrair informações valiosas sobre os mais diferentes temas me chamou a atenção e a partir dali comecei a pesquisar mais sobre isso, buscando como é essa área de atuação e o que é necessário para fazer parte dela.

Por um golpe do destino, em abril de 2021 a Alura abriu inscrição para a 3ª Imersão de Dados. Um curso intensivo de 1 semana mostrando os principais pontos de um projeto de Ciência de Dados. Ali eu não tinha conhecimento algum sobre a linguagem de programação Python e suas bibliotecas utilizadas ou sobre os modelos matemáticos e estatísticos mencionados durante as aulas, mas a maneira como os dados foram manipulados e analisados me interessaram muito.

Logo após a imersão foi aberta inscrição para o Bootcamp de Data Sciente Aplicada. Uma experiência de 12 semanas aprendendo sobre Python, as bibliotecas utilizadas para manipulação e visualização dos dados, análises de séries temporais e modelos de Machine Learning.

Esse é o projeto final desse **Bootcamp de Data Science Aplicada** que foi disponilizado pela [Alura Cursos Online](https://www.alura.com.br/). Nele serão aplicados os conhecimentos adquiridos nas últimas 12 semanas:
- **Tratamento dos dados**;
- **Análise Exploratória e visualização dos dados**;
- **Criação de Modelo de Machine Learning**;

Espero que esse projeto possa te auxiliar de alguma maneira, ou pelo menos despertar o interesse em conhecer mais sobre essa área.

<a name=intro></a>
## Introdução

Em dezembro de 2019 foi relatado o primeiro caso oficial de **Covid-19** causado pelo vírus SARS-CoV-2. No Brasil, em 26 de fevereiro de 2020 foi registrado o primeiro caso de Covid-19. Essa nova doença causou um estresse enorme sobre os sistemas de saúde dos países por não existir um tratamento com eficácia cientificamente comprovada. Para um parcela das pessoas infectadas os sintomas evoluem e se tornam severos ou críticos e assim necessitam de maiores cuidados. Esses pacientes precisam ser transferidos para a UTI e receber oxigênio.

Com o movimento desses pacientes para a UTI, ocorreu um **colapso do sistema de saúde** de diversos países ao redor do mundo, incluindo o **Brasil**.

Medidas foram tomadas para **aumentar o número de leitos de UTI** nos hospitais brasileiros, e também hospitais de campanha foram criados para atender um número maior de pacientes.

Para utilizar os leitos de UTI da melhor maneira possível, o Hospital Sírio-Libanês disponibilizou uma base de dados no Kaggle (pode ser verificada [aqui](https://www.kaggle.com/S%C3%ADrio-Libanes/covid19)) para incentivar a criação de Modelo de Machine Learning (Aprendizado de Máquina) que possam prever se um paciente necessitará ou não de um leito de UTI com base nos exames médicos realizados quando o paciente está no hospital.

Dessa maneira os pacientes que necessitam de um leito de UTI podem ser acomodados rapidamente em um leito livre, ou que possa ser buscado um leito em outro local, e os pacientes que não necessitarão de um leito podem ser acompanhados remotamente.

**Esse projeto explorará a base de dados fornecida pelo Hospital Sírio-Libanês e criará modelos de Machine Learning que façam a previsão da necessidade, ou não, de um leito de UTI.**

<a name=estrutura></a>
## Estrutura do Projeto

Esse projeto está dividido em 3 notebooks, conforme a descrição a seguir:

* [**Tratamento dos dados**](https://github.com/EltonGS/covid-19_previsao_leito_UTI/blob/main/Notebooks/1_tratamento_dados.ipynb): onde os dados serão tratados e manipulados.

* [**Análise Exploratória e Visualização dos Dados**](https://github.com/EltonGS/covid-19_previsao_leito_UTI/blob/main/Notebooks/2_analise_dos_dados.ipynb): onde os dados serão analisados e visualizados buscando o entendimento da base de dados.

* [**Modelo de Machine Learning**](https://github.com/EltonGS/covid-19_previsao_leito_UTI/blob/main/Notebooks/3_modelos_machine_learning.ipynb): onde serão criados os modelos de Machine Learning para previsão da necessidade de um leito de UTI para os pacientes com Covid-19.

<a name=dados></a>
## Informações sobre os dados

O **Hospital Sírio Libanês** compartilhou algumas informações sobre os dados:

- A coluna **ICU** é a que deve ser prevista utilizando um modelo de Machine Learning.

- A partir do momento que o valor na coluna **ICU** é **1** os dados não devem ser utilizados para o modelo de machine learning pois não é possível dizer se os exames foram feitos antes ou depois do paciente ser admitido na UTI.

- Os dados são anonimizados e foram coletados nas unidades de São Paulo e Brasília. Os dados foram anonimizados utilizando as melhores práticas internacionais.

- Os dados foram tratados e colocados em escala utilizando o método **Min Max Scaler** para estarem entre -1 e 1.

- Os dados disponíveis nessa base são:
> * Informação demográfica do paciente (03 colunas);
> * Agrupamento de doenças já existentes no paciente (09 colunas);
> * Resultados de exame de sangue (36 colunas);
> * Sinais vitais (06 colunas);

A equipe do Sírio Libanês também adicionou colunas com valores matemáticos e estatistícos dos exames de sangue e sinais vitais. Estes estão representados nas colunas com o nomes terminando em MEAN (média), MEDIAN (mediana), MAX (valor máximo), MIN (valor mínimo), DIFF (diferença entre o MAX e o MIN) e o DIFF_REL (A razão entre o DIFF e o MEDIAN).

**Dados Ausentes** - Os dados da tabela são provenientes de exames que são realizados com frequências diferentes. Por exemplo, medição dos sinais vitais são feitas a cada hora e exames laboratoriais de sangue são feitos semanalmente.

É razoável assumir que se os dados estão faltando para uma janela de tempo para um paciente é porque o paciente se manteve estável e apresentou resultados similares aos que já estavam registrados nas janelas anteriores ou posteriores. Assim os valores das janelas vizinhas podem ser utilizados para preencher os dados ausentes.

<a name=goals></a>
## Objetivos

Os objetivos indicados pelo Hospital Sírio Libanês são:

**Objetivo 1** - Prever a admissão à UTI de pacientes com Covid-19.

**Objetivo 2** - Prever a NÃO admissão à UTI de pacientes com Covid-19.

<a name=conclusao></a>
## Conclusão

Analisando a base de dados fornecida pelo Hospital Sírio Libanês foi possível identificar os seguintes fatores:

- A base de dados possui informações completas de 384 pacientes;
- 180 pacientes são idosos e 204 pacientes são não idosos;

A idade dos pacientes se mostra um fator importante para a admissão a UTI:

- Entre os pacientes idosos 66% (119) necessitou de um leito de UTI e 19 pacientes foram admitidos diretamente na UTI;
- Entre os pacientes não idosos 37% (76) necessitou de um leito de UTI;

---

Para realizar a previsão da necessidade de um leito de UTI foram testados 4 modelos de Machine Learning.

Os modelos de **Machine Learning** selecionados para esse projeto foram:

1. **Random Forest Classifier**
2. **Logistic Regression**
3. **SVC**
4. **LinearSVC**

O modelo com a melhor performance nas previsões foi o **Random Forest Classifier**, seguido de perto por **LinearSVC** e **Logistic Regression**.

O modelo **Random Forest Classifier** conseguiu as seguintes estatísticas:

 - prever corretamente **64%** dos pacientes que **necessitaram de um leito de UTI**;
 - prever corretamente **84%** dos pacientes que **NÃO necessitaram de um leito de UTI**;
 - o **AUC Médio** obtido através da validação cruzada foi **0.80**;

<a name=thanks></a>
## Agradecimentos

Esse projeto encerra o **Bootcamp de Data Science Aplicada** ministrado pela **Alura Cursos Online**, e com certeza INICIA minha jornada nesse mundo da Ciência de Dados.

Gostaria de agradecer a **Alura** pelas ótimas aulas e projetos, aos instrutores **Guilherme Silveira**, **Thiago Gonçalves**, **Karol Penteado** e **Allan Spadini**. Sempre dispostos a **compartilhar** seu conhecimento e explicar os conteúdos da melhor maneira possível.

Também agradecer ao **Scuba Team** e ao pessoal do **Student Experience**, sempre ajudando a todos no Discord.

E também agradecer a comunidade que se formou no Discord entre as pessoas realizando o Bootcamp, um ajudando ao outro, compartilhando ideias, conhecimento, dicas, memes...

<a name=refer></a>
## Referências utilizadas

1. [Página do Kaggle com informações sobre a base de dados](https://www.kaggle.com/S%C3%ADrio-Libanes/covid19)

2. [Text classification with extremely small datasets](https://towardsdatascience.com/text-classification-with-extremely-small-datasets-333d322caee2)

3. [5 Feature Selection Method From SciKit Learn You Should Know](https://towardsdatascience.com/5-feature-selection-method-from-scikit-learn-you-should-know-ed4d116e4172)

4. [Como Selecionar As Melhores Features Para Seu Modelo de Machine Learning](https://paulovasconcellos.com.br/como-selecionar-as-melhores-features-para-seu-modelo-de-machine-learning-2e9df83d062a)

5. [Machine Learning Map](https://scikit-learn.org/stable/tutorial/machine_learning_map/)

6. [Primeiro caso de Covid-19 pode ter atingindo a Chine em outubro](https://www.cnnbrasil.com.br/saude/primeiro-caso-covid-19-pode-ter-atingido-a-china-em-outubro-de-2019-diz-estudo/)

7. [Evolução dos Sintomas do Covid-19](https://saude.abril.com.br/medicina/casos-sem-sintomas-evolucoes-coronavirus/)

8. [Covid Impact to Global Healthcare](https://edition.cnn.com/videos/world/2021/04/14/covid-impact-global-healthcare-lon-orig.cnn)

9. [Observatório Covid-19 aponta maior colapso sanitário e hospitalar da história do Brasil](https://portal.fiocruz.br/noticia/observatorio-covid-19-aponta-maior-colapso-sanitario-e-hospitalar-da-historia-do-brasil)

10. [Primeiro caso Covid-19 no Brasil](https://saude.abril.com.br/medicina/coronavirus-primeiro-caso-brasil/)

11. [Overfitting e Underfitting em Machine Learning](https://abracd.org/overfitting-e-underfitting-em-machine-learning/#:~:text=Underfitting%20%C3%A9%20uma%20tradu%C3%A7%C3%A3o%20para,Overfitting%20%C3%A9%20o%20oposto)

12. [WHO delivers advice and support for older people during Covid-19](https://www.who.int/news-room/feature-stories/detail/who-delivers-advice-and-support-for-older-people-during-covid-19#:~:text=The%20COVID%2D19%20pandemic,potential%20underlying%20health%20conditions)

13. [Machine Learning in Healthcare](https://healthinformatics.uic.edu/blog/machine-learning-in-healthcare/)

14. [Machine Learning](https://www.ibm.com/cloud/learn/machine-learning)

15. [Hiperparameter Tuning](https://towardsdatascience.com/hyperparameter-tuning-c5619e7e6624)

16. [SKLearn Model Selection - RandomizedSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html)

17. [Entenda o que é AUC e ROC nos modelos de Machine Learning](https://medium.com/bio-data-blog/entenda-o-que-%C3%A9-auc-e-roc-nos-modelos-de-machine-learning-8191fb4df772)

18. [Understanding Confusion Matrix](https://towardsdatascience.com/understanding-confusion-matrix-a9ad42dcfd62)

19. [Understanding a Classification Report For Your Machine Learning Model](https://medium.com/@kohlishivam5522/understanding-a-classification-report-for-your-machine-learning-model-88815e2ce397)

20. [Understanding AUC ROC Curve](https://towardsdatascience.com/understanding-auc-roc-curve-68b2303cc9c5)

21. [Regressão Logística](https://pt.wikipedia.org/wiki/Regress%C3%A3o_log%C3%ADstica)

22. [SciKit Learn - RandomForestClassifier](http://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)

23. [SciKit Learn - Logistic Regression](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)

24. [SciKit Learn - SVC](http://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html)

25. [SciKit Learn - LinearSVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html)

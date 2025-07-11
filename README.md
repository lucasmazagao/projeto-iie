<h1>Análise estatística de variáveis com a ocorrência de AVC</h1>

<h2>Objetivos</h2>

<p>O relatório tem como objetivo identificar quais variáveis de um conjunto de dados estão estatisticamente associadas à ocorrência de acidente vascular cerebral (variável ‘stroke’). A intenção é verificar, com base em testes estatísticos, se as variáveis disponíveis na tabela de dados possuem influência significativa sobre a dependente, utilizando os testes de normalidade e de análise de variáveis.</p>

<p>O código está presente no link: <a href="https://colab.research.google.com/drive/16ElmbMhra_F96cJoM6JUddk586E2K-u_#scrollTo=EVlqiSORMtEo">colab.research.google.com</a></p>

<p>Foram avaliadas as seguintes variáveis como potenciais fatores explicativos:</p>
<ul>
  <li>gênero</li>
  <li>idade</li>
  <li>hipertensão</li>
  <li>doença cardíaca</li>
  <li>casamento</li>
  <li>tipo de trabalho</li>
  <li>residência</li>
  <li>fumante</li>
</ul>

<p>A variável de interesse é stroke, representando se o paciente teve ou não um AVC.</p>

<h2>1° Estatísticas descritivas das variáveis numéricas</h2>

<h3>Variável age/idade</h3>
<p>
A média de idade da amostra é de aproximadamente 43,23 anos, com um desvio padrão de 22,61 anos, indicando uma dispersão considerável ao redor da média. A mediana é 45 anos, enquanto o primeiro e terceiro quartis são, respectivamente, 25 e 61 anos. Isso mostra que 50% dos indivíduos estão entre 25 e 61 anos, indicando uma amostra predominantemente adulta. A diferença relativamente pequena entre a média e a mediana sugere que a distribuição de idade é aproximadamente simétrica.
</p>
<p>
Ademais, no box-plot, percebe-se que mais de 75% da população que sofreu AVC possui idade acima de 60 anos.
</p>

<h3>Variável hypertension/hipertensão</h3>
<p>
A variável é binária (0 = não tem hipertensão, 1 = tem). A média é de 0,097, o que corresponde a cerca de 9,7% da amostra com diagnóstico de hipertensão, com desvio padrão de 0,296. A mediana e os quartis são zero, o que indica que mais da metade da amostra não apresenta hipertensão.
</p>

<h3>Variável heart_disease/doença cardíaca</h3>
<p>
Também uma variável binária, apresenta uma média de 0,054 com desvio padrão de 0,226, indicando que 5,4% da amostra tem doença cardíaca. A mediana e os quartis são iguais a zero, o que confirma a forte predominância da ausência de doença cardíaca na população observada.
</p>

<h3>Variável stroke/AVC</h3>
<p>
A variável de interesse é binária (0 = sem AVC, 1 = com AVC). A média é 0,0487, o que significa que 4,87% dos indivíduos tiveram AVC, tendo desvio padrão de 0,215. A mediana e os quartis são todos iguais a zero, confirmando que a imensa maioria da amostra não sofreu AVC.
</p>

<h2>2° Teste de normalidade da variável dependente</h2>

<p>Antes da escolha dos testes estatísticos comparativos, foi realizada a verificação da normalidade de stroke, que é fundamental para determinar se testes paramétricos (como ANOVA ou t-test) seriam apropriados ou se testes não-paramétricos deveriam ser empregados. Para isso, foram aplicados os seguintes testes de normalidade: Shapiro-Wilk, Kolmogorov-Smirnov, e visualizando os gráficos por QQ-plot. Ademais, para todos os testes o nível de significância será de 0,05 ou 5%.</p>

<p>Os dois testes formais resultaram em p-valores próximos a 0,00, de forma que indica rejeição das hipóteses nulas. Sendo ambas ‘há evidência para normalidade dos dados’. Igualmente, no gráfico pode-se observar que os dados não seguem a linha teórica da normal. Sendo assim, consideramos que os dados não podem ser considerados normais, portanto, seguiremos com testes não-paramétricos.</p>

<h2>3° Teste e avaliação da influência das variáveis independentes</h2>

<p>Para investigar a relação entre as variáveis explicativas categóricas e a variável stroke, foram realizados testes estatísticos de comparação entre grupos. Empregando o teste Mann-Whitney U para variáveis com duas categorias, e Kruskal-Wallis para variáveis com três ou mais categorias. Sendo os resultados:</p>

<h3>Gênero (Kruskal-Wallis)</h3>
<p>O teste não indicou diferença estatisticamente significativa entre os grupos de gênero (masculino, feminino e outros), com p-valor de 0.7896. Portanto, não há evidência de que o gênero esteja associado à ocorrência de stroke.</p>

<h3>Hipertensão (Mann-Whitney U)</h3>
<p>O teste indicou p-valor de 6.12e-20. Isso mostra uma diferença estatística significativa entre pessoas com e sem hipertensão quanto à variável. Assim, a presença de hipertensão está associada à maior ocorrência de AVC.</p>

<h3>Doença Cardíaca (Mann-Whitney U)</h3>
<p>O teste indicou p-valor baixo de 5.25e-22, o que indica que indivíduos com histórico de doença cardíaca apresentam distribuição de stroke significativamente diferente dos que não possuem tal condição. Logo, há evidência de associação entre doença cardíaca e ocorrência de AVC.</p>

<h3>Casamento (Mann-Whitney U)</h3>
<p>O teste apresentou p-valor de 9.65e-15, o que confirma uma diferença significativa entre os grupos "casado" e "nunca casado" em relação a stroke. Portanto, o estado civil também é estatisticamente relevante na ocorrência de AVC.</p>

<h3>Tipo de Trabalho (Kruskal-Wallis)</h3>
<p>O teste indicou um p-valor de 5.42e-10, demonstrando que diferentes categorias de ocupação apresentam distribuições distintas da variável stroke. Assim, o tipo de trabalho exercido é um fator com associação estatística significativa à ocorrência de AVC.</p>

<h3>Residência (Mann-Whitney U)</h3>
<p>O teste resultou em p-valor de 0.2692, indicando que não há diferença significativa entre pessoas que moram em áreas urbanas ou rurais quanto à ocorrência de AVC.</p>

<h3>Fumante (Kruskal-Wallis)</h3>
<p>O p-valor de 2.09e-06 mostra uma associação estatisticamente significativa entre tabagismo e stroke. Indivíduos que fumam ou fumaram apresentam distribuições distintas de ocorrência de AVC em comparação com os que nunca fumaram ou com status desconhecido.</p>

<h2>4° Conclusões</h2>

<p>A análise estatística revelou que as seguintes variáveis têm associação estatisticamente significativa com a ocorrência de AVC (stroke):</p>
<ul>
  <li>idade</li>
  <li>hipertensão</li>
  <li>doença cardíaca</li>
  <li>casamento</li>
  <li>tipo de trabalho</li>
  <li>fumante</li>
</ul>

<p>Por outro lado, as variáveis gênero e tipo de residência não apresentaram associação significativa com a ocorrência de AVC.</p>

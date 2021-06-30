# Amostragem com Probabilidades Proporcionais ao Tamanho {#ppt}
<div style="text-align: justify">
A *Amostragem com Probabilidades Proporcionais ao Tamanho - PPT* agrega alguns métodos de seleção de amostra onde as unidades da população têm probabilidades distintas de seleção, proporcionais a uma medida de tamanho associada a cada unidade.

## Motivação

Como já indicado no Capítulo \@ref(visger), a *Amostragem Probabilística* contempla o emprego de métodos de amostragem que levam a ter probabilidades de inclusão na amostra desiguais, isto é, $\pi_i \ne \pi_j$ para algum par de unidades distintas $i \ne j \in U$. A teoria apresentada no Capítulo \@ref(visger) cobre o caso geral, mas não indica quando o recurso de usar probabilidades desiguais de inclusão na amostra seria vantajoso. Neste capítulo tratamos justamente dessa questão, indicando estratégias que se pode usar para tirar proveito do emprego de amostragem com probabilidades desiguais para aumentar a eficiência dos estimadores de totais e médias.

A ideia central já mencionada na Seção \@ref(propHT) é fazer com que as probabilidades de inclusão fiquem proporcionais aos valores da(s) variável(is) de estudo $y$. É claro que não podemos conseguir isso de forma exata, já que os valores da variável $y$ são desconhecidos antes da seleção da amostra. Mas em muitas situações práticas é possível contar com cadastros que contenham valores de uma variável auxiliar $x$ indicativa do tamanho das unidades populacionais. Sempre que a variação dos tamanhos das unidades for grande, a informação auxiliar disponível sobre os tamanhos for precisa e o tamanho for positivamente correlacionado com as variáveis de interesse, podemos empregar métodos de seleção que usam probabilidades proporcionais ao tamanho. Tais métodos permitem aumentar a eficiência na estimação de totais e médias, em comparação com métodos de amostragem com probabilidades iguais, para tamanhos de amostra idênticos.

## Estimação do total populacional

Considere o caso em que os valores de uma variável auxiliar $x$ são conhecidos para todas as unidades da população $U$ mediante um cadastro. Se $x_i>0, \,\, \forall \, i \in U$, então podemos usar esta variável como uma *medida de tamanho* das unidades populacionais. Por enquanto, vamos supor que é possível selecionar amostras de acordo com um plano amostral tal que: $\pi_i \propto x_i, \,\,\forall\, i \in U$. Mais adiante, apresentamos diversos métodos para implementar essa ideia.

Conforme já mostrado no Capítulo \@ref(visger), sabemos que o estimador HT para estimar o total populacional $Y = \sum_{i \in U} y_i$ é dado por:

$$
\widehat Y_{HT} = \displaystyle \sum_{i \in s} \frac{y_i}{\pi_i} = \displaystyle \sum_{i \in s} d_i y_i \,\, (\#eq:eqppt1)
$$
onde cada unidade da amostra tem um peso amostral igual ao inverso da respectiva probabilidade de inclusão, dado por $d_i = 1 / \pi_i, \,\, \forall \, i \in U$.

Quando a probabilidade de inclusão na amostra é proporcional ao tamanho, temos:
$\pi_i = n{x_i} / {X}$ 
onde $X = \sum_{i \in U} x_i$ é o total populacional da variável $x$ e $n$ é o tamanho da amostra. 

Sendo assim, o peso amostral da unidade $i$ é dado por $d_i = X / (n x_i)$. Substituindo na Expressão \@ref(eq:eqppt1), o estimador HT do total $Y$ fica dado por:

$$
\widehat Y_{HT/PPT} = \displaystyle X\frac{1}{n} \sum_{i \in s} \frac{y_i}{x_i}  \,\, (\#eq:eqppt2)
$$
Verifica-se então que, para amostras extraídas com probabilidades de inclusão exatamente proporcionais ao tamanho, o estimador de total depende de estimar a *média das razões* entre a variável de interesse $y$ e a medida de tamanho $x$ e, depois, multiplicar essa estimativa pelo total conhecido da medida de tamanho na população. Essa forma de apresentar o estimador de total sugere que, sempre que as razões ${y_i}/{x_i}$ forem aproximadamente constantes, a média amostral delas será um estimador preciso da correspondente média populacional, e o estimador de total terá variância pequena.

Uma forma de ver isto mais diretamente requer lembrar da expressão alternativa para a variância do estimador HT, válida para planos amostrais de tamanhos fixos, a chamada forma SYG (Sen-Yates-Grundy) da variância, dada por:

$$
\begin{align} V_{SYG} \left( \widehat Y_{HT/PPT} \right) & = \displaystyle \sum_{i \in U} \sum_{j>i} (\pi_i \pi_j - \pi_{ij}) \left( \frac{y_i}{\pi_i} - \frac{y_j}{\pi_j} \right)^2 \\
& = \displaystyle X^2 \frac{1}{n^2} \sum_{i \in U} \sum_{j>i} (\pi_i \pi_j - \pi_{ij}) \left( \frac{y_i}{x_i} - \frac{y_j}{x_j} \right)^2 \end{align} \,\, (\#eq:eqppt3)
$$

Da Expressão \@ref(eq:eqppt3) podemos observar que a variância do estimador de total seria nula caso $y_i/x_i = y_j/x_j$ para todo $i \neq j \in U$. Portanto, se $y_i \propto x_i \,\,\forall\, i \in U$, então $V_{SYG}\left( \widehat Y_{HT} \right) = 0$. Isto sugere que se $y$ e $x$ forem aproximadamente proporcionais (logo, alta e positivamente correlacionadas), então a variância do estimador HT do total será pequena.

Também se pode notar que a variância deveria ser pequena quando $\pi_{ij} \doteq \pi_i \pi_j, \,\, \forall \, i \neq j \in U$. Acontece que $\pi_{ij} = \pi_i \pi_j, \,\, \forall \, i \neq j \in U$ implica indicadores de inclusão das unidades $i$ e $j$ independentes. Um plano amostral satisfazendo essa propriedade é a *Amostragem de Poisson*, apresentado adiante. Entretanto, *Amostragem de Poisson* não é eficiente, como veremos, devido à variabilidade do tamanho amostral efetivo, e também não podemos usar a expressão de variância na forma SYG para esse plano amostral, justamente porque não tem tamanho amostral fixo.

Sendo assim, a chave para alcançar eficiência através da amostragem PPT é ter medidas de tamanho $(x)$ alta e positivamente correlacionadas com a(s) resposta(s) de interesse na pesquisa $(y)$. Essa situação é muitas vezes encontrada ao realizar pesquisas de estabelecimentos ou instituições, onde as principais variáveis de estudo da pesquisa são bem correlacionadas com medidas de tamanho frequentemente disponíveis nos cadastros empregados para seleção das respectivas amostras.

A seleção de amostras com PPT pode ser feita com ou sem reposição. O sorteio de amostras com reposição é pouco usado na prática, devido à perda de eficiência em comparação com métodos de sorteio sem reposição e também ao problema prático do que fazer em caso de repetição de unidades selecionadas. Apesar disso, é importante conhecer este método e suas propriedades, pois com frequência é usado como aproximação para obter estimativas simplificadas de variância. Já na amostragem PPT sem reposição há vários métodos de seleção, trazendo mais complexidade e dificuldades na estimação da precisão. Porém a eficiência é maior e se justifica o emprego de métodos mais complexos. 

Na sequência apresentamos os principais métodos de sorteio de amostras PPT, com e sem reposição. Para um tratamento mais completo dos métodos disponíveis, consultar @Brewer1983.

## Amostragem PPT com reposição

O algoritmo para seleção de amostra com *Probabilidades Proporcionais ao Tamanho com Reposição - PPTC* é denominado *método dos totais cumulativos* e consiste nos seguintes passos: 

1. Acumule as medidas de tamanho na população, isto é, faça $X_{(0)} = 0$ e calcule $X_{(i)} = \displaystyle \sum_{k=1}^{i} x_k$ para $i=1,...,N$.
2. Determine *intervalos de seleção* com base no tamanho de cada unidade. Assim, o intervalo de seleção para a unidade $i$ será dado por $(X_{(i-1)} ; X_{(i)}]$, sendo o limite superior incluído, para $i=1,...,N$. 
3. Selecione um número aleatório $r$ com distribuição uniforme entre 0 e $X_{(N)} = X$, a soma dos tamanhos na população.
4. Selecione a unidade correspondente ao intervalo no qual cai o número aleatório $r$, isto é, selecione $i$ tal que $r \in (X_{(i-1)} ; X_{(i)}]$.
5. Repita os passos 3 e 4 tantas vezes quantas forem necessárias para obter a amostra do tamanho $n$ desejado.

A *Amostra selecionada* $s$ é constituída pelas unidades $i_1, ..., i_l, ..., i_n$ cujos rótulos foram sorteados nas várias iterações do passo 4.

Amostragem PPT com reposição é um método muito simples de implementar, mas que pode implicar seleção repetida de unidades. O tamanho efetivo da amostra (número de unidades distintas na amostra) é aleatório, podendo ser menor que o tamanho total desejado $(n)$. O Exemplo \@ref(exm:exmppt1) ilustra o emprego do método com uma pequena população para ajudar a compreensão.

**(#exm:exmppt1)** Considere a população de $N=6$ fazendas com as respectivas áreas, conforme apresentada na Tabela \@ref(tab:tabppt1). Este exemplo mostra como extrair uma amostra de $n=3$ fazendas usando PPT com reposição, tomando a variável Área como medida de tamanho, usando o *método dos totais cumulativos*.

<center>
<table>
<caption>(#tab:tabppt1)Informações das áreas, em hectares, de uma população de $N=6$ fazendas</caption>
</table>
----------
 Fazenda    Área (ha)  Tamanho Acumulado   Limite inferior do intervalo   Limite superior do intervalo
--------- ----------- ------------------ ------------------------------ ------------------------------
   1          50          50                          1	                               50
   
   2       1.000       1.050	                       51	                            1.050
   
   3         125       1.175	                    1.051	                            1.175
   
   4         300       1.475	                    1.176	                            1.475
   
   5         500       1.975	                    1.476	                            1.975
   
   6          25       2.000	                    1.976	                            2.000
----------
</center>

Caso os 3 números aleatórios sorteados de forma independente e com distribuição Uniforme entre 1 e 2.000 fossem 654, 1.230 e 1.555, então as fazendas selecionadas seriam as de números 2, 4 e 5. Caso os 3 números aleatórios entre 1 e 2.000 fossem 122, 754 e 1.980, então as fazendas 2 e 6 seriam as selecionadas, com a fazenda 2 sendo selecionada duas vezes.

Pode-se programar no R o algoritmo apresentado ou utilizar a função *ppswr* do pacote *pps* que disponibiliza várias funções para seleção de amostras PPT de vários tipos.


```r
#Algoritmo de seleção PPT
# Inicializando variáveis
N=6
n=3
fazenda=c(1:N)
area=c(50,1000,125,300,500,25)
acum=linf=lsup=sel=NULL
acum[1]=lsup[1]=area[1]
linf[1]=1
sel=rep(0,N)
# Criando intervalos de seleção
for (i in 2:N){
  acum[i]=acum[i-1]+area[i]
  linf[i]=acum[i-1]+1
  lsup[i]=acum[i]
}
# Selecionando n números aleatórios entre 1 e o tamanho total acumulado
s=sample(1:lsup[N],n)
# Contando número de vezes que cada fazenda foi selecionada
for (i in 1:n){
  for (j in 1:N){
    if((linf[j] <= s[i]) & (lsup[j]>=s[i])){
      sel[j]=sel[j]+1
    }
  }
}
# Juntando as informações numa tabela
tabela=data.frame(cbind(fazenda,area,acum,linf,lsup,sel))
# Aleatórios selecionados
s
```

```
## [1]  124  908 1362
```

```r
# Tabela com os dados e marcação do número de vezes que cada fazenda foi selecionada
tabela
```

```
##   fazenda area acum linf lsup sel
## 1       1   50   50    1   50   0
## 2       2 1000 1050   51 1050   2
## 3       3  125 1175 1051 1175   0
## 4       4  300 1475 1176 1475   1
## 5       5  500 1975 1476 1975   0
## 6       6   25 2000 1976 2000   0
```

```r
# Resolvendo o mesmo problema utilizando função de um pacote do R
# Carregando o pacote pps, para seleção proporcional ao tamanho
require(pps)
```

```
## Carregando pacotes exigidos: pps
```

```r
# Selecionando fazendas com a função de seleção proporcional ao tamanho com reposição
fazendas_sel=ppswr(area,n)
# Identificação das fazendas selecionadas
fazendas_sel
```

```
## [1] 2 5 5
```

Nas duas seleções apresentadas no programa R, os resultados são diferentes pois são selecionados números pseudoaleatórios distintos nas duas soluções.

### Estimação do total sob amostragem PPT com reposição

Um estimador não viciado do total sob amostragem PPT com reposição - PPTC é dado por: 

$$
\widehat Y_{PPTC} = \frac{1}{n} \sum_{i \in s} \frac{f_i y_i}{p_i} \,\, (\#eq:eqppt4) 
$$

onde $f_i$ representa o número de vezes que a unidade $i$ foi incluída na amostra $s$ e $p_i = x_i / X$ é o tamanho relativo da unidade $i$. Note que o número de unidades distintas no conjunto $s$ pode ser menor que $n$ e também que $\sum_{i \in s} f_i = \sum_{i \in U} f_i = n$.

Note que o estimador não viciado para o total da Expressão \@ref(eq:eqppt4) não é o estimador tipo HT. Este estimador foi proposto por @Hansen1943, por isso é chamado de estimador de Hansen-Hurwitz - HH, e é também não viciado. O estimador HT também pode ser empregado com este plano amostral, mas precisaria do cálculo das probabilidades de inclusão de primeira ordem das unidades populacionais, dadas por:

$$
\pi_i = 1 - (1  -p_i)^n
$$
A principal vantagem do estimador HH aqui apresentado é a simplicidade referente à estimação de variâncias. Não há resultados genéricos indicando em que situações a variância do estimador HH seria menor que a do estimador HT.

A variância de $\widehat Y_{PPTC}$ e o seu respectivo estimador não viciado são dados por: 

$$
V_{PPTC}\left(\widehat  Y_{PPTC}\right) = \frac{1}{n} \displaystyle \sum_{i \in U} \left( \frac{y_i}{p_i} - Y \right)^2 p_i \,\, (\#eq:eqppt5) 
$$

$$
\widehat V_{PPTC} \left(\widehat Y_{PPTC}\right) = \frac{1}{n(n-1)} \displaystyle \sum_{i \in s} f_i \left( \frac{y_i}{p_i} - \widehat Y_{PPTC} \right)^2 \,\,(\#eq:eqppt6)
$$

Como já discutido anteriormente, métodos de seleção com reposição raramente são empregados na prática, pois sempre é possível aplicar métodos sem reposição de maior eficiência para o mesmo custo. Por esse motivo, passamos agora a discutir alguns dos muitos métodos disponíveis para sorteio de amostras com *PPT sem reposição*. Nossa seleção de métodos a apresentar se guiou fortemente pela relevância da aplicação destes métodos em pesquisas conduzidas no Brasil, que vamos citar como exemplos ao longo da discussão.

## Amostragem PPT de Poisson

O método de *Amostragem PPT de Poisson* ou, simplesmente, *Amostragem de Poisson - PO* para seleção de amostras com PPT sem reposição é implementado mediante a realização de uma prova de Bernoulli independente para cada unidade da população, que determina se a unidade é incluída (ou não) na amostra com uma probabilidade proporcional ao seu tamanho. Caso todas as probabilidades de inclusão na amostra sejam iguais, este método se reduz à *Amostragem Binomial* e, portanto, este método é uma generalização daquele método.

Um algoritmo baseado em processamento sequencial de lista para implementar o método PPT de Poisson para selecionar uma amostra de tamanho $n$ da população $U$ de tamanho $N$ consiste nos seguintes passos:

1. Para cada unidade populacional $i$, determine o valor da probabilidade de inclusão $\pi_i = n x_i / X = n p_i$.
2. Para cada unidade da população selecione, de forma independente, um número aleatório $A_i$ com distribuição uniforme no intervalo [0;1].
3. Inclua a unidade $i$ na amostra se $A_i \le \pi_i$.

O conjunto $s$ de unidades selecionadas por este algoritmo não terá unidades repetidas e terá um tamanho efetivo aleatório, de valor esperado igual a $n$. 

Alguns cuidados devem ser observados ao implementar a *Amostragem PPT de Poisson*. Em primeiro lugar, verifique se nenhuma unidade tem tamanho relativo $x_i / X$ maior que $1/n$. Se isto ocorrer, a ‘probabilidade de inclusão’ desta unidade seria maior que 1, o que é impossível. Caso alguma unidade seja tão grande que $x_i / X > 1/n$, inclua esta unidade com certeza (isto é, faça $\pi_i = 1$). Em seguida, refaça os cálculos dos $\pi_i$ com o tamanho desta unidade excluído do total $X$ e o tamanho de amostra diminuído de uma unidade. Repita a verificação até que nenhuma unidade tenha tamanho relativo maior que 1 sobre o tamanho residual da amostra.

A seguir mostramos uma implementação em R do algoritmo de seleção para *Amostragem PPT de Poisson*.

**(#exm:exmppt2)** Vamos utilizar os dados do arquivo 'MunicBR_dat.rds' para selecionar uma amostra de municípios do Amazonas, de tamanho esperado $n=20$, utilizando *Amostragem PPT de Poisson*.


```r
#Algoritmo de seleção PPT de Poisson com seleção certa das unidades
# muito grandes, se for o caso
# Lendo a identificação e população dos municípios do Amazonas
tabela <- readRDS(file="Dados/MunicBR_dat.rds")[75:136,c(1, 4)]
#Ordenação dos tamanhos em ordem decrescente
tabela=tabela[order(tabela$Pop,decreasing=T),]
N=length(tabela$Pop)
n=20
sel=A=pii=rep(0,N)
X=sum(tabela$Pop)
# Verificando as unidades com seleção "certa" pelo tamanho
for (i in 1:N){
  pii[i]=n*tabela$Pop[i]/X
  if (pii[i]>=1){
# Seleção certa: sel=1    
    sel[i]=1                   
    X=X-tabela$Pop[i]
    pii[i]=1
    n=n-1
  }
}
# Gerando aletório U(0,1) para cada unidade da população
# e incluindo ou não na amostra por seleção aleatória
for (i in 1:N){
  if (sel[i] < 1){
    A[i]=runif(1,0,1)
    pii[i]=n*tabela$Pop[i]/X
# Seleção aleatória: sel=2
    if (A[i]<=pii[i]) {sel[i]=2} 
  }
}
# Juntando as informações numa tabela
tabela$ai=A
tabela$pii=pii
tabela$sel=sel
# Amostra com os dados das unidades selecionadas certas(sel=1) e aleatórias(sel=2)
tabela[tabela$sel>0,]
```

```
##     CodMunic     Pop          ai       pii sel
## 112  1302603 1982177 0.000000000 1.0000000   1
## 120  1303403  109225 0.000000000 1.0000000   1
## 103  1301902   94278 0.445112481 0.9886311   2
## 110  1302504   91795 0.419109556 0.9625935   2
## 94   1301209   81325 0.422922206 0.8528015   2
## 132  1304203   62885 0.182700458 0.6594334   2
## 84   1300607   37564 0.090222171 0.3939088   2
## 92   1301100   35431 0.369191620 0.3715415   2
## 117  1303106   33829 0.287529744 0.3547424   2
## 96   1301407   33127 0.044493482 0.3473809   2
## 87   1300706   32792 0.148006335 0.3438680   2
## 83   1300508   29737 0.300445181 0.3118323   2
## 82   1300409   27110 0.141294725 0.2842846   2
## 111  1302553   26530 0.019448636 0.2782026   2
## 101  1301803   25362 0.138432125 0.2659545   2
## 125  1303700   24327 0.103456878 0.2551012   2
## 98   1301605   21859 0.009403678 0.2292209   2
## 136  1304401   20091 0.131798316 0.2106810   2
## 134  1304260   12801 0.048941290 0.1342356   2
## 89   1300839   12004 0.097493720 0.1258780   2
## 76   1300060   10436 0.092501309 0.1094354   2
## 106  1302108    6083 0.017440692 0.0637884   2
```

A amostragem PPT de Poisson é o método que foi empregado para a seleção da amostra da Pesquisa Industrial Anual - Produção Física, do IBGE, de 1981. 

A *Amostragem PPT de Poisson* é pouco usada na prática devido à variabilidade do tamanho efetivo da amostra. É um método menos eficiente que outros métodos de seleção PPT sem reposição. Um método moderno que corrige este defeito é *Amostragem Sequencial de Poisson - ASP* - ver @Ohlsson1998 - descrito na Seção \@ref(ASP).

### Estimação do total sob amostragem de Poisson 

O estimador HT do total sob amostragem de Poisson é dado por: 

$$
\widehat Y_{PO} = \sum_{i \in s} \frac{y_i} {\pi_i} =  \frac{1}{n} \sum_{i \in s} \frac{y_i}{p_i} \,\,(\#eq:eqppt7)
$$

A variância de $\widehat Y_{PO}$ e um estimador não viciado desta variância são dados por: 

$$
V_{PO} \left( \widehat Y_{PO} \right) = \displaystyle \sum_{i \in U} \pi_i (1 - \pi_i) \left( \frac{y_i}{\pi_i} \right)^2 = \displaystyle \sum_{i \in U} \frac{(1 - \pi_i)}{\pi_i} y_i^2 \,\, (\#eq:eqppt8) 
$$

$$
\widehat V_{PO} \left( \widehat Y_{PO} \right) = \displaystyle \sum_{i \in s} (1 - \pi_i) \left( \frac{y_i}{\pi_i} \right)^2 = \displaystyle \sum_{i \in s} \frac{(1 - \pi_i)}{\pi_i^2} y_i^2 \,\, (\#eq:eqppt9) 
$$

Como ocorre na *Amostragem Binominal*, devido ao tamanho efetivo da amostra ser variável, também é possível usar um estimador de total tipo razão sob *Amostragem de Poisson*. Tal estimador é mais eficiente do que o estimador HT. Este estimador tipo razão é dado por:

$$
\widehat Y_{PO}^R = \frac{N}{\widehat N} \sum_{i \in s} d_i {y_i} = N \frac{\sum_{i \in s} d_i {y_i}}{\sum_{i \in s} d_i } \,\,(\#eq:eqppt10)
$$

A variância aproximada de $\widehat Y_{PO}^R$ e um estimador consistente desta variância são dados por:

$$
V_{PO}\left(\widehat  Y_{PO}^R \right) \doteq \frac {N}{N-1} \frac{1}{n} \displaystyle \sum_{i \in U} (1 - n p_i) \left( \frac{y_i}{p_i} - Y \right)^2 p_i \,\, (\#eq:eqppt11) 
$$
e

$$
\widehat V_{PO}\left(\widehat Y_{PO}^R \right) = \frac{1}{n(m-1)} \displaystyle \sum_{i \in s} (1 - n p_i) \left( \frac{y_i}{p_i} - \widehat Y_{PO}^R \right)^2 \,\, (\#eq:eqppt12) 
$$
onde $m$ é o tamanho efetivo da amostra selecionada. Para mais detalhes sobre a estimação da variância, ver @Ohlsson1998.

## Amostragem sequencial de Poisson  {#ASP}

O método de *Amostragem Sequencial de Poisson - ASP*, proposto por @Ohlsson1998, é uma modificação do método de *Amostragem de Poisson* que elimina a variabilidade do tamanho efetivo da amostra. O custo dessa modificação é um procedimento de amostragem um pouco mais complexo e que requer uso de resultados aproximados para a estimação tanto do total como de sua variância.

Um algoritmo baseado em processamento sequencial de lista para implementar o método para selecionar uma amostra de tamanho $n$ da população $U$ consiste nos seguintes passos.

1. Gere um número aleatório uniforme independente $A_i$ para cada unidade $i$ da população.
2. Calcule a medida de tamanho relativo $p_i = x_i / X$ para cada unidade $i$ da população.
3. Calcule o *número aleatório modificado* $C_i = A_i / p_i$.
4. Ordene as unidades crescentemente segundo os valores dos números aleatórios modificados $C_i$.
5. Selecione para a amostra as $n$ unidades com os menores valores de $C_i$.

**(#exm:exmppt3)** Seleção de uma amostra de $n=10$ municípios do Acre, a partir do arquivo 'MunicBR_dat.rds', por *Amostragem Sequencial de Poisson*, utilizando o R.


```r
# Algoritmo para Amostragem sequencial de Poisson
# Lendo a identificação e a população dos municípios do Acre
tabela <- readRDS(file="Dados/MunicBR_dat.rds")[53:74,c(1, 4)]
N=length(tabela$Pop)
n=10
# Gerando números aleatórios ai~U(0,1)
tabela$ai=runif(N,0,1)
X=sum(tabela$Pop)
# Calculando os tamanhos relativos pi
tabela$pi=tabela$Pop/X
# Calculando os aleatórios modificados ci
tabela$ci=tabela$ai/tabela$pi
# Ordenando as linhas da tabela segundo ci
tabela=tabela[order(tabela$ci),]
# Tomando as n primeiras linhas da tabela ordenada
# como a amostra desejada
amostra=tabela[1:n,]
amostra
```

```
##    CodMunic    Pop         ai         pi         ci
## 55  1200104  22899 0.01982249 0.02949142  0.6721442
## 60  1200302  32411 0.03730163 0.04174185  0.8936268
## 67  1200401 357194 0.56969805 0.46002707  1.2384012
## 58  1200203  80377 0.24648989 0.10351684  2.3811573
## 71  1200500  40311 0.49201240 0.05191619  9.4770515
## 59  1200252  16099 0.31311494 0.02073376 15.1016936
## 53  1200013  13353 0.26530298 0.01719721 15.4270910
## 72  1200609  37571 0.82485744 0.04838737 17.0469587
## 74  1200807  16029 0.35555683 0.02064361 17.2235777
## 65  1200385  17795 0.49266786 0.02291803 21.4969578
```

### Estimação com amostragem sequencial de Poisson

O estimador tipo HT do total sob *Amostragem Sequencial de Poisson* é dado por: 

$$
\widehat Y_{ASP} = \frac{1} {n} \sum_{i \in s} \frac{y_i}{p_i} \,\, (\#eq:eqppt13) 
$$

A variância aproximada de $\widehat Y_{ASP}$ é dada por: 

$$\hspace{-1,0cm}
V_{ASP}\left(\widehat Y_{ASP}\right) \doteq \frac{N}{N-1} \frac{1}{n} \displaystyle\sum_{i \in U} (1-np_i) \left(\frac{y_i}{p_i} - Y \right)^2  p_i = V_{PO}\left(\widehat  Y_{PO}^R \right) \,\,(\#eq:eqppt14) 
$$
Vemos assim que a variância do estimador de total sob Amostragem Sequencial de Poisson é, praticamente, a mesma que se obteria usando o estimador de razão sob Amostragem de Poisson. A principal vantagem é que sob ASP o tamanho efetivo da amostra é fixo. Um estimador consistente desta variância é dado por:

$$
\widehat V_{ASP}\left(\widehat Y_{ASP}\right) = \frac{1}{n(n-1)} \displaystyle\sum_{i \in s}\left(\frac{y_i}{p_i} - \widehat Y_{ASP}\right)^2 (1-np_i)p_i\,\,(\#eq:eqppt15) 
$$
No Brasil, ASP foi usada para a seleção de escolas para aplicação de testes padronizados no âmbito do Sistema de Avaliação da Educação Básica - SAEB, como descrito em @Bussab1999. 


## Amostragem sistemática com PPT

O método de *Amostragem Sistemática com PPT - SIS* consiste nos seguintes passos:

1. Acumule as medidas de tamanho na população, isto é, e faça $X_{(0)}=0$ e calcule $X_{(i)}=\displaystyle \sum_{k=1}^{i}x_k$ para $i=1,...,N$.
2. Determine “intervalos de seleção” com base no tamanho de cada unidade. Assim, o intervalo de seleção para a unidade $i$ será dado por $(X_{(i-1)};X_{(i)}]$, sendo o limite superior incluído.
3. Determine o intervalo de amostragem através do salto $\displaystyle K=\frac{X_{(N)}}{n}=$ Total dos Tamanhos/Tamanho da Amostra.
4. Selecione um número aleatório $r$ (ponto de partida) com distribuição uniforme entre 0 e $K$.
5. Selecione as unidades correspondentes aos intervalos nos quais caem os valores $r+(j-1) K$, para $j=1,2,...,n$. Isto é, selecione toda unidade $i$ tal que $r+(j-1) K \in (X_{(i-1)};X_{(i)}]$, para $j=1,2,...,n$. 

Seguem alguns cuidados a serem tomados no uso da Amostragem Sistemática com PPT:

* Verifique se alguma unidade tem tamanho $x_i$ maior que $K$. Se isto ocorrer, esta unidade seria incluída ‘com repetição’ na amostra, o que é indesejável.
* Caso alguma unidade seja tão grande que $x_i > K$, inclua esta unidade com certeza na amostra, e refaça os cálculos para $K$ com o tamanho desta unidade excluído do total e o tamanho de amostra diminuído de uma unidade.
* Repita a verificação até que nenhuma unidade tenha tamanho maior que o intervalo de seleção calculado no passo 3.

### Amostragem PPT sistemática com ordenação

A seleção com amostragem PPT sistemática com ordenação segue os seguintes passos:

1. Faça uma ordenação das unidades da população segundo uma (ou mais) variável(is) de interesse.
2. Selecione uma amostra sistemática com PPT seguindo o algoritmo anterior.

Apresentamos uma implementação do algoritmo para seleção Sistemática com PPT, considerando como certas as unidades em que o valor da variável tamanho é maior que $K$. Dessa maneira a seleção é sem reposição.

**(#exm:exmppt4)**  O arquivo 'MunicBR_dat.rds' apresenta alguns dados sobre os municípios brasileiros. Vamos tomar os dados de Rondônia e selecionar uma amostra de tamanho $n=10$ municípios, com probabilidades proporcionais à população de cada município.


```r
# Seleção Sistemática com PPT e seleção das unidades certas se for o caso
# Inicializando variáveis
# Lendo a identificação e população dos municípios de Rondônia
tabela <- readRDS(file="Dados/MunicBR_dat.rds")[1:52,c(1, 4)]
N=length(tabela$Pop)
n=10
certas=aleat=sel=selc=r=NULL
# Ordenação dos tamanhos em ordem decrescente
tabela=tabela[order(tabela$Pop,decreasing=T),] 
sel=rep(0,N)
#Determinando tamanho mínimo das unidades certas
n_aux=n
tamtot_aux=tam_certo=sum(tabela$Pop)
for (i in 1:N){
  p=n_aux*tabela$Pop[i]/tamtot_aux
  if (p>=1){
    tam_certo=tabela$Pop[i]
    p=1
    n_aux=n_aux-1
    tamtot_aux=tamtot_aux-tabela$Pop[i]
    # Seleção certa: sel=1
    sel[i]=1
  }
}
aleat=tabela
if (sum(sel)>0){
  certas=tabela[tabela$Pop>=tam_certo,]
  aleat=tabela[tabela$Pop<tam_certo,]
  selc=sel[sel>0]
} 
# Seleção aleatória sistemática PPT
acum=linf=lsup=sel=NULL
acum[1]=lsup[1]=aleat$Pop[1]
linf[1]=1
N=length(aleat$Pop)
sel=rep(0,N)
# Criando intervalos de seleção PPT
for (i in 2:N){
  acum[i]=acum[i-1]+aleat$Pop[i]
  linf[i]=acum[i-1]+1
  lsup[i]=acum[i]
}
# Salto de seleção
K=lsup[N]/n_aux                     
# Partida aleatória
r[1]=runif(1,0,K)                   
if (n_aux>1){for (i in 2:n_aux){r[i]=r[i-1]+K}} 
# Marcando fazendas selecionadas aleatoriamente
for (i in 1:n_aux){
  for (j in 1:N){
    if((linf[j] < r[i]) & (r[i]<=lsup[j])){
      #Seleção aleatória: sel=2
      sel[j]=2           
    }
  }
}
# Juntando as informações da seleção
tabela$sel=c(selc,sel)
# Amostra com marcação das unidades selecionadas certas(sel=1) e aleatórias(sel=2)
tabela[tabela$sel>0,]
```

```
##    CodMunic    Pop sel
## 17  1100205 484992   1
## 12  1100122 128026   2
## 2   1100023 101269   2
## 22  1100304  87727   2
## 11  1100114  55597   2
## 15  1100155  40099   2
## 9   1100098  31699   2
## 32  1100809  22973   2
## 25  1100346  17399   2
## 51  1101757  10518   2
```

Esta forma de implementar a Amostragem Sistemática PPT confere um efeito de ‘estratificação implícita’ pela variável (ou variáveis) usada(s) na ordenação. 

**(#exm:exmppt5)** Nas pesquisas domiciliares por amostragem do IBGE, anteriores à adoção da amostra mestra para o Sistema Integrado de Pesquisas Domiciliares - SIPD,  tais como na PNAD, POF e PME, era usual adotar a seleção sistemática com PPT. No caso da PNAD, o plano amostral incluía a seleção de municípios, que eram estratificados por tamanho em termos de população e selecionados sistematicamente com probabilidade proporcional à população residente obtida no último Censo Demográfico. Antes da seleção dos setores, arrolava-se em cada município selecionado, primeiramente, os setores urbanos em ordem crescente de numeração e, posteriormente, os setores rurais. Os setores eram selecionados, em cada município da amostra, também sistematicamente com probabilidade proporcional utilizando como medida de tamanho o número de unidades domiciliares existentes por ocasião do último Censo Demográfico. Nas demais pesquisas domiciliares, onde a unidade primária de seleção era o setor, era feita a seleção dos setores em cada estrato sistematicamente com PPT (medido em número de domicílios ou domicílios particulares ocupados). Detalhes sobre os principais aspectos de amostragem das pesquisas domiciliares do IBGE podem ser vistos em @Albieri2015. Cabe registrar que, para a estimação da precisão das estimativas, eram adotados estimadores das variâncias como se o plano amostral fosse de seleção PPT com reposição.  

A Amostragem Sistemática com PPT (com ou sem ordenação) era muito usada na prática por sua simplicidade na seleção de amostras. Porém, com o advento de modernas ferramentas computacionais que permitem selecionar com facilidade amostras PPT sem reposição usando outros métodos, tornou-se menos popular.

Quando *Amostragem Sistemática com PPT* for usada para selecionar a amostra, pode-se usar o estimador HT para o total conforme descrito na Expressão \@ref(eq:eqppt2). Para esse plano amostral, a variância tem uma expressão complexa e não há estimador consistente de variância disponível na literatura. O problema da estimação de variância sob amostragem sistemática com PPT é ainda mais difícil quando o sorteio é feito com ordenação. @Berger2003 oferece uma estratégia que pode ser considerada nesse caso.

## Amostragem PPT de Pareto

A seleção com *Amostragem PPT de Pareto - AP*, de acordo com @Rosen2000, segue os seguintes passos:

1. Gere número aleatório uniforme independente $A_i$ para cada unidade $i$ da população.
2. Calcule a *probabilidade de inclusão desejável* da unidade $i: \lambda_i = n x_i/X$.
3. Calcule o número aleatório modificado $\displaystyle C_i=\frac{A_i(1-\lambda_i)}{(1-A_i)\lambda_i}$.
4. Ordene as unidades crescentemente segundo valores dos números aleatórios modificados $C_i$.
5. Selecione para a amostra as $n$ unidades com os menores valores de $C_i$.

**(#exm:exmppt6)** Vamos repetir o Exemplo \@ref(exm:exmppt3), agora utilizando seleção por *Amostragem PPT de Pareto*.


```r
# Algoritmo para Amostragem PPT de Pareto
# Lendo a identificação e a população dos municípios do Acre
tabela <- readRDS(file="Dados/MunicBR_dat.rds")[53:74,c(1, 4)]
N=length(tabela$Pop)
n=10
# Gerando números aleatórios ai~U(0,1)
tabela$ai=runif(N,0,1)
X=sum(tabela$Pop)
# Probabilidade de inclusão desejável da unidade
tabela$lambdai=n*tabela$Pop/X
# Calculando os aleatórios modificados ci
tabela$ci=tabela$ai*(1-tabela$lambdai)/((1-tabela$ai)*tabela$lambdai)
# Ordenando as linhas da tabela segundo ci
tabela=tabela[order(tabela$ci),]
# Tomando as n primeiras linhas da tabela ordenada
# como a amostra desejada
amostra=tabela[1:n,]
amostra
```

```
##    CodMunic    Pop         ai   lambdai           ci
## 58  1200203  80377 0.99792200 1.0351684 -16.31524848
## 67  1200401 357194 0.38403138 4.6002707  -0.48793267
## 72  1200609  37571 0.08176717 0.4838737   0.09498394
## 65  1200385  17795 0.03208026 0.2291803   0.11147413
## 64  1200351  15857 0.02948550 0.2042209   0.11838557
## 66  1200393  10143 0.06561180 0.1306308   0.46731873
## 68  1200427  15968 0.12102517 0.2056505   0.53184016
## 55  1200104  22899 0.20845891 0.2949142   0.62964125
## 70  1200450  20799 0.42143969 0.2678685   1.99092170
## 59  1200252  16099 0.35673141 0.2073376   2.12011348
```

A *Amostragem PPT de Pareto* é o método empregado para sorteio de unidades primárias de amostragem da PNAD Contínua - ver @Freitas2014.

Para tamanhos de amostra iguais, AP é mais eficiente que ASP. A implementação deste método requer os mesmos cuidados com relação a unidades muito grandes que com outros métodos PPT sem reposição. As probabilidades exatas de inclusão não são estritamente proporcionais ao tamanho e são difíceis de calcular. Porém, resultados sugerem que as aproximações consideradas no passo 2 são suficientemente boas para a maioria das situações de interesse prático, como pode ser visto em @Aires2005.

### Estimação do total sob amostragem PPT de Pareto

O estimador do total sob Amostragem PPT de Pareto - AP é dado por: 

$$
\widehat Y_{AP} = \displaystyle\sum_{i \in s}\frac{y_i}{\lambda_i} = \frac{1}{n}\sum_{i \in s}\frac{y_i}{p_i}\,\,(\#eq:eqppt16) 
$$

Note que $E_{AP} \left(\widehat Y_{AP}\right)\doteq Y$. A variância de $\widehat Y_{AP}$ e o seu respectivo estimador são dados, segundo @Rosen2000, por: 

$$\hspace{-0,5cm}
V_{AP} \left(\widehat Y_{AP}\right) \doteq \frac{N}{N-1} \displaystyle \sum_{i \in U} \left(\frac{y_i}{\lambda_i} - \frac{\sum_{k \in U} y_k(1 - \lambda_k)} {\sum_{k \in U} \lambda_k(1 - \lambda_k)}\right)^2 \lambda_i(1 - \lambda_i) \,\, (\#eq:eqppt17)
$$

$$
\widehat V_{AP} \left(\widehat Y_{AP}\right) = \frac{n}{n-1} \displaystyle\sum_{i \in s} \left(\frac{y_i}{\lambda_i} - \frac{\sum_{k \in s} y_k(1-\lambda_k)/\lambda_k} {\sum_{k \in s} (1-\lambda_k)}\right)^2 (1-\lambda_i) \,\,\, (\#eq:eqppt18) 
$$

A Tabela \@ref(tab:tabppt2) apresenta um resumo de estimadores do total e  respectivas variâncias sob os diversos métodos de seleção com PPT apresentados neste capítulo. 

<table>
<caption>(#tab:tabppt2)Estimadores do total e respectivas variâncias sob PPT</caption>
</table>
<center>
----------
Estimador
-------------------------------------------     
$\widehat Y_{PPTC} = \displaystyle\frac{1}{n} \sum_{i \in s} \frac{f_i y_i}{p_i}$

$\displaystyle\widehat Y_{PO} = \sum_{i \in s} \frac{y_i} {\pi_i} =  \frac{1}{n} \sum_{i \in s} \frac{y_i}{p_i}$

$\widehat Y_{PO}^R =\displaystyle \frac{N}{\widehat N} \sum_{i \in s} d_i {y_i} = N \displaystyle\frac{\sum_{i \in s} d_i {y_i}}{\sum_{i \in s} d_i }$ 
   
$\widehat Y_{ASP} = \displaystyle\frac{1} {n} \sum_{i \in s} \frac{y_i}{p_i}$ 

$\widehat Y_{AP} = \displaystyle\sum_{i \in s}\frac{y_i}{\lambda_i} = \frac{1}{n}\sum_{i \in s}\frac{y_i}{p_i}$
                                            
$\widehat V_{PPTC} \left(\widehat Y_{PPTC}\right)=\displaystyle\frac{1}{n(n-1)}\displaystyle \sum_{i \in s} f_i \left( \frac{y_i}{p_i}-\widehat Y_{PPTC}\right)^2$ 

$\widehat V_{PO} \left( \widehat Y_{PO} \right) = \displaystyle \sum_{i \in s} \frac{(1 - \pi_i)}{\pi_i^2} y_i^2$

$\widehat V_{PO}\left(\widehat Y_{PO}^R \right) = \displaystyle\frac{1}{n(m-1)} \displaystyle \sum_{i \in s} (1 - n p_i) \left( \frac{y_i}{p_i} - \widehat Y_{PO}^R \right)^2$

$\widehat V_{ASP}\left(\widehat Y_{ASP}\right) = \displaystyle\frac{1}{n(n-1)} \displaystyle\sum_{i \in s}\left(\frac{y_i}{p_i} - \widehat Y_{ASP}\right)^2 (1-np_i)p_i$

$\widehat V_{AP} \left(\widehat Y_{AP}\right) =\displaystyle \frac{n}{n-1} \displaystyle\sum_{i \in s} \left(\frac{y_i}{\lambda_i} - \frac{\sum_{k \in s} y_k(1-\lambda_k)/\lambda_k} {\sum_{k \in s} (1-\lambda_k)}\right)^2 (1-\lambda_i)$

----------
</center>

## Exercícios {#exerc10}

**(#exr:exrppt1)** Verifique que o estimador de HT da média não é invariante sob transformações de locação. Isto é, se tomarmos $z_i=y_i+A$, então $\overline z_{HT}\ne\overline y_{HT}+A$. 

**(#exr:exrppt2)** Uma amostra foi selecionada usando o método PPT com reposição. As informações dessa amostra aparecem na Tabela \@ref(tab:tabppt3).
  
<center>
<table>
<caption>(#tab:tabppt3)Informações obtidas na amostra selecionada</caption>
</table>
----------
 Unidade    $p_i$   $y_i$   $\pi _i$
--------- ------- ------- ----------
  6         0,02     45    
 
  8         0,01     20     0,0297 
 
 14         0,03     60     0,0873 
----------
</center>

a) Calcule o valor de $\pi_i$ que está faltando. 
b) Estime o total populacional da variável de interesse, $y$, usando o estimador de Horvitz-Thompson.
b) Estime a variância da estimativa calculada em b usando o estimador HT e o estimador alternativo apresentado.
c) Compare e comente os resultados obtidos.
  
**(#exr:exrppt3)** No arquivo 'fazendas_dat.rds' são listadas 338 fazendas, com informações sobre a receita e a despesa de cada uma.  Suponha que não são conhecidas as informações sobre as despesas e que se deseja selecionar uma amostra de 20 fazendas para estimar a despesa média da população de fazendas.

a) Selecione uma AAS de 20 fazendas e construa um IC<sub>95%</sub> para a despesa média das fazendas.
b) Selecione uma amostra PPT com reposição de 20 fazendas, considerando a variável receita como tamanho, e construa um IC<sub>95%</sub> para a despesa média das fazendas.
c) Compare os resultados com a despesa média verdadeira das 338 fazendas e teça seus comentários.

**(#exr:exrppt4)** (@Thompson2012) Uma determinada região tem 320 lagos que somados cobrem uma área de 80 km<sup>2</sup>. Num estudo sobre poluição das águas, foi selecionada uma amostra de lagos, seguindo o procedimento abaixo: 

  * Um retângulo de comprimento C e largura L foi desenhado sobre um mapa da região. 
  * Pares de números aleatórios uniformes entre 0 e 1 foram gerados. O primeiro número de cada par foi multiplicado por C e o segundo por L, dando coordenadas dentro da região em estudo. 
  * Se a coordenada “caísse” sobre um lago no mapa, este era selecionado para a amostra. 
  * O procedimento foi repetido até que 4 pontos “caíssem” sobre algum lago. 
  * O primeiro lago da amostra foi selecionado 2 vezes.

Nos lagos selecionados foi medido o nível de poluição. Os resultados estão na Tabela \@ref(tab:tabppt4):

<center>
<table>
<caption>(#tab:tabppt4)Informações obtidas para os lagos selecionados</caption>
</table>
-----------             
 Lago          Poluição   Tamanho do lago 
        (partes/milhão)  (km<sup>2</sup>)
------ ---------------- -----------------
 1          2                        1,2 
 
 1          2                        1,2 
 
 2          5                        0,2 
 
 3         10                        0,5
-----------
</center>
a. Qual o tipo de amostragem utilizada? 
b. Calcule uma estimativa não viciada para a média de poluição dos lagos da região. 
c. Estime a variância do estimador utilizado.
  
**(#exr:exrppt5)** Sejam $U=\{1,\;2,\;...,\;i,\;...,\;N\}$ o conjunto de $N$ rótulos distintos de uma população e $Y_U = \{y_1,\;y_2,\;...,\;y_i,\;..., \;y_N\}$ um vetor populacional de interesse. Uma amostra com probabilidades desiguais com reposição de tamanho $n$ foi selecionada de $U$ para estimar o total $Y = \sum_{i \in U} y_i$, sendo o vetor amostral representado por $y_s = \{y_1, y_2, \dots, y_n\}$ e $\{p_1, p_2, \dots, p_N\}$ o conjunto das probabilidades de seleção das unidades populacionais num dado sorteio, tais que $\sum_{i \in U} p_i=1$. Antes de efetivar a observação da amostra, $y_1, y_2, \dots, y_n$ são variáveis aleatórias independentes e identicamente distribuídas - IID.

a)  Descreva a distribuição de probabilidades comum dos $y_i$ e calcule a esperança e a variância dessa distribuição.
b)  Obtenha um estimador não viciado para o total $Y$ com base na amostra e prove que esse estimador é mesmo não viciado, usando a distribuição obtida no item a.

       
**(#exr:exrppt6)** Considere a população de empresas descrita na Tabela \@ref(tab:tabppt5). Utilizando o R, resolva as questões.

a)  Selecione uma amostra aleatória simples sem reposição de 3 empresas.
b)  Use a amostra selecionada em a. para estimar a Receita média das empresas na população e o correspondente CV.
c)  Selecione uma amostra com probabilidades proporcionais ao Pessoal Ocupado, com reposição, de 3 empresas.
d)  Use a amostra selecionada no item c para estimar a Receita média das empresas na população e o correspondente CV.
e)  Compare os resultados das duas amostras com os valores verdadeiros e comente esses resultados.
  
<center>
<table>
<caption>(#tab:tabppt5)Dados populacionais das empresas</caption>
</table>
----------
 Empresa   Pessoal            Receita\
           Ocupado       (1.000 Reais)
--------- -------- -------------------
     1      250         8.000

     2      350        12.000

     3      175         6.000

     4      310        10.000

     5      160         5.000

     6      350        18.000

     7      375        18.000

     8      150         4.000

     9      275         9.000

    10      240         8.000
----------
</center>
       
**(#exr:exrppt7)** Seja o arquivo de dados 'MunicBR_dat.rds'. Selecione uma amostra de 10 municípios com PPT, utilizando como medida de tamanho a variável população (Pop).

a)  Estime o total da população para o Brasil.
b)  Compare com o valor verdadeiro e comente esse resultado surpreendente. Por que isso ocorre?

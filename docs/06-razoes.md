# Estimação de Razões e Funções de Totais {#razao}
<div style="text-align: justify">
## Razões populacionais como parâmetros de interesse

Muitas vezes, na prática de pesquisas por amostragem, o *parâmetro* populacional de interesse é uma razão entre os totais (ou médias) de duas variáveis de pesquisa definidas para cada unidade da população. Nesse caso, o *parâmetro* é denominado *razão de totais (ou de médias)* ou simplesmente *razão*. Chamando de $y$ e $x$ as variáveis cujos totais aparecem no numerador e denominador da razão, respectivamente, define-se a *razão* $R$ como:

$$
R = \frac{\sum_{i\in U}y_i}{\sum_{i\in U}x_i} = \frac{Y}{X}=\frac{\overline{Y}}{\overline{X}} (\#eq:eqraz1)
$$
 
Alguns exemplos de razões de interesse incluem:

- A razão entre o total dos gastos com transporte e o total da renda das famílias.
- A produtividade da lavoura de certo produto, definida como a razão entre o total da quantidade colhida do produto pelo total da área plantada com esse produto.
- O salário médio dos trabalhadores da indústria, definido como a razão entre o total dos salários dos trabalhadores da indústria e o número total de trabalhadores da indústria.
- A densidade de pessoas por dormitório em domicílios particulares, definida como a razão entre o número de pessoas residentes em domicílios particulares e o número total de dormitórios em domicílios particulares.

No caso da razão entre o total dos gastos com transporte $(y)$ e o total da renda das famílias $(x)$, a razão fica definida como:

$$
\frac{\textrm {Total dos gastos com transporte}}{\textrm{Total da renda}} = \frac{\sum_{i\in U}y_i}{\sum_{i\in U}x_i}=\frac{Y}{X} = R 
$$
 
## Razão de médias *versus* média de razões

Um cuidado importante aqui é compreender o significado do parâmetro de interesse. A razão de totais $R$ não é a média $\left(\overline{R} = \sum_{i\in U}{r_i}/{N} \right)$ das *razões por unidade* $\left(r_i=y_i/x_i\right)$. Neste capítulo estamos interessados na razão de totais (ou médias) e não na média de razões. A média de razões $\left(\overline{R} \right)$ pode ser estimada usando os estimadores habituais de médias populacionais discutidos no Capítulo \@ref(visger), aplicados à variável $r$ definida aqui.

**(#exm:exmrazao1)** Considere as densidades de habitantes por área (em km<sup>2</sup>) das unidades da federação brasileiras apresentadas na Tabela \@ref(tab:tabrazao1), conforme o Censo 2010. Neste exemplo, vemos como uma discrepância grande pode ocorrer entre as duas quantidades (a razão de médias e a médias das razões), quando os valores de $r_i$  são muito dispersos.

<center>
<table>
<caption>(#tab:tabrazao1)Densidade demográfica por Unidade da Federação, média das razões e razão das médias para o Brasil</caption>
</table>
--------- 
                                Densidade                                            Densidade
Unidade da                    demográfica              Unidade da                    demográfica
Federação                  Hab/km<sup>2</sup>          Federação                    Hab/km<sup>2</sup>
----------------------- ----------------     --------- ---------------------- -------------  
Rondônia                    6,6                        Sergipe                      94,4

Acre                        4,5                        Bahia                        24,8

Amazonas                    2,2                        Minas Gerais                 33,4

Roraima                     2,0                        Espírito Santo               76,3
 
Pará                        6,1                        Rio de Janeiro              365,2

Amapá                       4,7                        São Paulo                   166,3 

Tocantins                   5,0                        Paraná                       52,4

Maranhão                   19,8                        Santa Catarina               65,3

Piauí                      12,4                        Rio Grande do Sul            39,8

Ceará                      56,8                        Mato Grosso do Sul            6,9

Rio Grande do Norte        60,0                        Mato Grosso                   3,4

Paraíba                    66,7                        Goiás                        17,7

Pernambuco                 89,6                        Distrito Federal            444,1
        
Alagoas                   112,3 
 
${\bf\text{Brasil}}^1$    **68,1**                     ${\bf\text{Brasil}}^2$      **22,4**
--------- 
</center> $^1$Média de razões, $^2$Razão de médias    
 Fonte: IBGE, Censo Demográfico 2010.

Os dados apurados na última linha da Tabela \@ref(tab:tabrazao1) ilustram bem a importância de identificar corretamente que parâmetro se deseja estimar. No exemplo aqui considerado, a densidade demográfica apurada no nível do País como um todo é 22,4 Hab/km<sup>2</sup>, enquando a média das densidades demográficas calculadas por unidades da federação é de 68,1 Hab/km<sup>2</sup>, mais que três vezes maior. Portanto, ao enfrentar uma situação em que o parâmetro de interesse pode ser caracterizado como uma das duas situações, cabe ao responsável por planejar a pesquisa esclarecer, junto aos demandantes da mesma, qual dos dois conceitos melhor descreve a quantidade de interesse. Isto permitirá selecionar adequadamente o estimador que deve ser empregado com os dados da amostra a ser coletada.

## Outras funções de totais

*Totais* são parâmetros muito importantes, pois muitos outros parâmetros de interesse podem ser obtidos como funções de totais. Já vimos no Capítulo \@ref(proporc) o exemplo das contagens de unidades pertencentes a determinados grupos que possuem características comuns, no caso em que as variáveis cujos totais se quer estimar são indicadoras da pertinência a tais grupos. No Capítulo \@ref(visger) também verificamos que as médias populacionais são razões de totais, onde no denominador aparece o número, $N$, de unidades na população e no numerador vai o total da variável cuja média se quer definir. 

Neste capítulo, já definimos as *razões de totais* populacionais, e agora vamos apresentar mais alguns parâmetros que podem ser definidos como funções de totais populacionais. Para introduzir o caso mais geral, considere um parâmetro $\theta$ que pode ser definido como uma função de $K$ totais populacionais, isto é:

$$ 
 \theta = f(Y_1, Y_2, ..., Y_K) 
$$

onde $Y_k$ é o total populacional da variável de pesquisa $y_k$, para $k=1,...,K$, e $f$ é uma função real que especifica como obter o valor de $\theta$ a partir dos totais das variáveis de pesquisa.

Um caso geral de interesse é o das funções lineares de totais populacionais, dadas por:

$$
 \theta = f(Y_1, Y_2, ..., Y_K) = \sum_{k=1}^K a_k \, Y_k (\#eq:eqraz2)
$$

onde $a_k$ são constantes conhecidas, para $k=1,...,K$.

Um exemplo simples de função linear é a *diferença* entre dois totais populacionais especificados, dada por:

$$
 D = \sum_{i\in U} y_{2i} - \sum_{i\in U} y_{1i} = Y_2 - Y_1
$$

Nesse caso, temos uma situação envolvendo $K=2$ totais populacionais, com $a_1 = 1$ e $a_2 = -1$. 

Outro exemplo de parâmetro que pode ser escrito como função de totais é o caso da *função de distribuição cumulativa* num ponto, dada por:

$$
 F_y(a) = \displaystyle \frac{1}{N} \sum_{i\in U} I(y_i \le a) \quad
$$

Nesse caso, a situação envolve apenas dois totais populacionais $(K=2)$, sendo a primeira definida como $y_{1i} = I(y_i \le a)$ e a segunda $y_{2i} = 1$, e a função definida como $f(Y_1, Y_2) = Y_1 / Y_2$.

A *variância* de uma variável de pesquisa $y$, dada por

$$
 S^2_y = \frac{1}{N-1} \left[ \sum_{i\in U} {y_i}^2 - N \overline{Y}^2 \right] = \frac{1}{N-1} \left[ \sum_{i\in U} {y_i}^2 -  {Y}^2/N \right]
$$

também pode ser vista como uma função envolvendo três totais populacionais $(K=3)$, sendo o primeiro definido como total da variável $y_{1i} = y_i^2$, o segundo $y_{2i} = y_i$ e o terceiro como $y_{3i} = 1$. A função que retorna a variância $S^2_y$ é definida como 
$f(Y_1, Y_2, Y_3) = \frac {1} {Y_3 - 1} \left[ Y_1 - (Y_2^2/Y_3) \right]$.

De maneira similar, a *covariância* e a *correlação* das variáveis $y$ e $z$ podem ser definidas como:

$$
S_{y , z} = \displaystyle \frac{1}{N-1} \sum_{i\in U} \left({y_{i} - \overline{Y}} \right)  \left({z_{i} - \overline{Z}} \right) = \frac{1}{N-1} \left[ \sum_{i\in U} {y_{i}} {z_{i}} - \, Y Z / {N} \right] \quad  
$$

e

$$
{\rho}_{y , z} = \frac{S_{y , z}} {S_{y} S_{z}}
$$

A covariância pode ser vista como uma função envolvendo quatro totais populacionais $(K=4)$, sendo o primeiro definido como o total $Y_1$ da variável $y_{1i} = y$, o segundo o total $Y_2$ da variável $y_{2i} = z$, o terceiro o total da variável definida como $y_{3i} = y_{i} z_{i}$ e o quarto o total da variável definida como $y_{4i} = 1$. Por simplicidade, a função que define a correlação foi definida em função da covariância e dos desvios-padrão das duas variáveis de interesse, mas também poderia ser escrita como função de totais como já ilustrado nos demais casos.

O ponto importante a destacar nesta seção é o fato de que muitos parâmetros de interesse podem ser vistos como funções de totais populacionais e, com isso, podem também ser estimados aplicando as funções que definem os parâmetros a estimadores dos totais correspondentes. Isto corresponde essencialmente a uma espécie de *método dos momentos* para estimar parâmetros populacionais, onde cada total populacional desconhecido é substituído na expressão do parâmetro por um estimador amostral não viciado do total correspondente.

Essa ideia pode ser aplicada de maneira bastante geral para obter estimadores para grande quantidade de parâmetros populacionais que possam ser escritos em função de totais populacionais de variáveis bem definidas. Para fixar as ideias, este método é aplicado primeiramente para obter estimador para uma *razão de totais*. 

## Estimadores de razões de totais

Para estimar *razões de totais* (ou de médias) como $R$, o estimador “natural” é a *razão dos estimadores Horwitz-Thompson de total*:

$$
\widehat{R} = \frac{ \sum_{i\in s} w_i y_i} {\sum_{i\in s} w_i x_i} = \frac{ \widehat{Y}_{HT} } {\widehat{X}_{HT}} (\#eq:eqraz3)
$$

**Notas:**

1. Tanto o numerador como o denominador do estimador $\widehat{R}$ da razão $R$ podem variar com a amostra selecionada, $s$.    
2. Apesar de termos estimadores não viciados para os totais populacionais $\widehat{Y}_{HT}$ e $\widehat{X}_{HT}$, em geral,  $E(Z/W) \ne E(Z)E(W)$, e portanto:     
$$
E(\widehat{R}) = E(\widehat{Y}_{HT}/ \widehat{X}_{HT}) \ne E(\widehat{Y}_{HT})/E(\widehat{X}_{HT})= {Y} / {X} = R
$$    
3. Logo $\widehat{R}$ é um *estimador viciado* de $R$.    
4. O vício de $\widehat{R}$ é pequeno e chamado de *vício técnico*, para distingui-lo de outros vícios potencialmente causados por problemas tais como erros de cobertura, não resposta e outros. Para amostras grandes (isto é, com $n$ grande), este vício é geralmente desprezível do ponto de vista prático. Ver discussão na Seção \@ref(vicioraz).    
5. Sob AAS, como os pesos amostrais são constantes (e iguais a $N/n$ para todas as unidades da amostra), o estimador $\widehat{R}$ simplifica para:
$$
\widehat{R}_{AAS} = \frac{\sum_{i\in s} y_i} {\sum_{i\in s} x_i} = \frac{\overline{y}} {\overline{x}} (\#eq:eqraz4)
$$


## Estimadores para outras funções de totais {#estoft}

Quando o parâmetro de interesse é uma função de totais populacionais $\theta = f(Y_1, Y_2, ..., Y_K)$, o método mais simples para estimar esse parâmetro é aplicar a mesma função a estimadores não viciados dos totais, isto é, usar o estimador:

$$
\widehat{\theta} = f(\widehat{Y}_1, \widehat{Y}_2, ..., \widehat{Y}_K) (\#eq:eqraz5)
$$

onde $\widehat{Y}_k$ é o estimador HT do total populacional da variável de pesquisa $y_k$, para $k=1,...,K$.

Para o caso de *funções lineares*, o estimador resultante será dado por:

$$
 \widehat{\theta} = \sum_{k=1}^K a_k \, \widehat{Y}_k (\#eq:eqraz6)
$$

e será um estimador não viciado do parâmetro $\theta$. 

Neste caso, a variância do estimador também é relativamente simples de obter, e dada por:

\begin{eqnarray}
V_p \left( \widehat{\theta} \right) & = & 
\sum_{k=1}^K \sum_{j = 1}^K a_k \, a_j COV_p \left( \widehat{Y}_k ,  \widehat{Y}_j \right) \\
 &=& \sum_{k=1}^K a^2_k \, V_p \left( \widehat{Y}_k \right) +  \sum_{k=1}^K \sum_{j \ne k = 1}^K a_k \, a_j COV_p \left( \widehat{Y}_k ,  \widehat{Y}_j \right) \\ \hfill(\#eq:eqraz7)
\end{eqnarray}

e um estimador dessa variância pode ser facilmente construído usando:

\begin{eqnarray}
\widehat{V}_p \left( \widehat{\theta} \right) & = & \sum_{k=1}^K \sum_{j = 1}^K a_k \, a_j \widehat{COV}_p \left( \widehat{Y}_k ,  \widehat{Y}_j \right) \\
& = & \sum_{k=1}^K a^2_k \, \widehat{V}_p \left( \widehat{Y}_k \right) +  \sum_{k=1}^K \sum_{j \ne k = 1}^K a_k \, a_j \widehat{COV}_p \left( \widehat{Y}_k ,  \widehat{Y}_j \right) \\ \hfill(\#eq:eqraz8)
\end{eqnarray}

Um resultado bastante útil é mostrado a seguir. Quando $\theta = \sum_{k=1}^K a_k \, Y_k$, então sua variância pode ser escrita como:

\begin{eqnarray}
V_p \left( \widehat{\theta} \right) & = & E_p \left( \widehat{\theta} -\theta \right)^2 \\ 
& = & E_p \left( \sum_{k=1}^K a_k \widehat{Y_k} -  \sum_{k=1}^K a_k Y_k \right)^2 \\
& = & E_p \left( \sum_{k=1}^K a_k \sum_{i \in s} \pi_i^{-1} y_{ki} - \sum_{k=1}^K a_k \sum_{i \in U} y_{ki} \right)^2 \\
& = & E_p \left[ \sum_{i \in s} \pi_i^{-1} \left( \sum_{k=1}^K a_k y_{ki} \right) - \sum_{i \in U} \left( \sum_{k=1}^K a_k y_{ki} \right) \right]^2 \\
& = & E_p \left( \sum_{i \in s} \pi_i^{-1} z_i - \sum_{i \in U} z_i \right)^2 \\
& = & E_p \left( \widehat{Z}_{HT} - Z \right)^2 \\
& = & V_p \left( \widehat{Z}_{HT} \right)\\ \hfill (\#eq:eqraz9)
\end{eqnarray}

onde $z_i = \sum _{k=1} ^K a_k y_{ki}$.

Verifica-se assim que a variância do estimador para $\theta$ pode ser obtida como a variância de um estimador de total para uma *variável derivada* $z$ definida de maneira apropriada, tornando assim a obtenção da variância do estimador do parâmetro uma tarefa mais simples, já que a variância de estimadores de total foi apresentada no Capítulo \@ref(visger). Isso leva também à obtenção de estimadores da variância de forma simples, usando a mesma variável derivada:

$$
\widehat{V}_p \left( \widehat{\theta} \right) = \widehat V_{HT}(\widehat{Z}_{HT}) = \displaystyle \sum_{i \in s} \sum_{j \in s} \left( {d_i d_j} - {d_{ij}} \right) {z_i} {z_j}  (\#eq:eqraz10)
$$

Este resultado tem utilidade também quando $\theta$ é uma função não linear de totais, mas essa função é contínua e diferenciável. Neste caso, é possível usar a técnica de *linearização de Taylor* para obter a variância aproximada do estimador e também um estimador para essa variância. A ideia dessa técnica é simples: aproximar o estimador não linear por uma quantidade linearizada, obtida a partir da expansão em Série de Taylor do estimador $\widehat{\theta}$ ao redor do ponto $\theta$. A expansão é dada por:

$$
\begin{eqnarray}
 \widehat{\theta} & = & f(\widehat{Y}_1, \widehat{Y}_2, ..., \widehat{Y}_K) \\
 & = & f(Y_1, Y_2, ..., Y_K) + \sum_{k=1}^K \left[ \frac {\partial {f(Y_1, Y_2, ..., Y_K)}}   {\partial{Y_k}} \right] \left( \widehat{Y}_k - Y_k \right) + \\
 & \, & +\sum_{q=2}^\infty \frac {1} {q!} \sum_{k=1}^K \left[ \frac {\partial ^q {f(Y_1, Y_2, ..., Y_K)}} {\partial {Y^q_k}} \right] \left( \widehat{Y}_k - Y_k \right)^q \\
 & \doteq & f(Y_1, Y_2, ..., Y_K) + \sum_{k=1}^K \left[ \frac {\partial {f(Y_1, Y_2, ..., Y_K)}}   {\partial{Y_k}} \right] \left( \widehat{Y}_k - Y_k \right)\\ \hfill (\#eq:eqraz11)
\end{eqnarray}
$$
onde a aproximação da última linha advém da exclusão de todos os termos de ordem igual ou superior a 2.

É comum chamar de $\widehat{\theta}_L$ a quantidade:

$$
\begin{eqnarray}
 \widehat{\theta}_L & = & f(Y_1, Y_2, ..., Y_K) + \sum_{k=1}^K \left[ \frac {\partial {f(Y_1, Y_2, ..., Y_K)}} {\partial{Y_k}} \right] \left( \widehat{Y}_k - Y_k \right) \\
 & = & \theta + \sum_{k=1}^K a_k \left( \widehat{Y}_k - Y_k \right) 
\end{eqnarray}
$$ 
onde agora $a_k = \displaystyle\frac {\partial {f(Y_1, Y_2, ..., Y_K)}} {\partial{Y_k}}$, $k=1, 2, ..., K$.

Assim sendo, a obtenção da variância aproximada para o estimador não linear $\widehat{\theta}$ é feita calculando-se a variância do *estimador linearizado* $\widehat{\theta}_L$, que é dada por:

$$
\widehat{V}_p \left( \widehat{\theta} \right) \doteq \widehat{V}_p \left( \widehat{\theta}_L \right) = \widehat V_{HT} (\widehat{Z}_{HT}) = \displaystyle \sum_{i \in s} \sum_{j \in s} \left( {d_i d_j} - {d_{ij}} \right) {z_i} {z_j} (\#eq:eqraz12)
$$

onde $z_i =\displaystyle\sum_{k=1}^K \frac{\partial {f(Y_1, Y_2, ..., Y_K)}} {\partial{Y_k}} \, y_{ki}$.

## Análise do vício do estimador da razão {#vicioraz}

Para analisar o vício do estimador da razão, note que:

$$
\begin{eqnarray}
COV_p \left( \widehat{R} , \widehat{X} \right) & = & E_p \left( \widehat{R}  \widehat{X} \right) - E_p \left( \widehat{R} \right)  E_p \left( \widehat{X} \right) \\
 & = &  E_p \left( \frac{ \widehat{Y} } { \widehat{X} }  \widehat{X} \right) - E_p \left( \widehat{R} \right)  E_p \left( \widehat{X} \right) \\
 & = &  E_p \left( \widehat{Y} \right) - E_p \left( \widehat{R} \right)  E_p \left( \widehat{X} \right) \\ 
 & = & Y - E_p \left( \widehat{R} \right)  X
\end{eqnarray}
$$

Segue-se então que:

\begin{eqnarray}
E_p \left( \widehat{R} \right) & = & \frac{Y}{X} - \frac{1}{X}  COV_p \left( \widehat{R} , \widehat{X} \right) \\
 & = & R - \frac{1}{X}  COV_p \left( \widehat{R} , \widehat{X} \right)
\end{eqnarray}

Chamando agora de $B_p( \widehat{R} ) = E_p \left( \widehat{R} \right) - R$, o vício do estimador $\widehat{R}$, mostrou-se que este pode ser obtido como:

$$
B_p( \widehat{R} ) = - \frac{1}{X}  COV_p \left( \widehat{R} , \widehat{X} \right) (\#eq:eqraz13)
$$

Esta expressão fornece um caminho para estabelecer um limite superior para o valor absoluto do vício dividido pelo desvio padrão do estimador da razão. Notando que: $COV_p \left( \widehat{R} , \widehat{X} \right) = CORR_p \left( \widehat{R} , \widehat{X} \right)  DP_p(\widehat{R})  DP_p(\widehat{X})$, segue-se que:

\begin{eqnarray}
 \left| \frac {B_p( \widehat{R} )}{DP_p(\widehat{R})} \right| & = & \frac{1}{X}  \left| \frac{CORR_p \left( \widehat{R} , \widehat{X} \right)  DP_p(\widehat{R})  DP_p(\widehat{X})} {DP_p(\widehat{R})} \right| \\ 
 & = & \left| CORR_p \left( \widehat{R} , \widehat{X} \right) \right|  \frac {DP_p(\widehat{X})}{X} \le CV_p(\widehat{X}) \\ \hfill(\#eq:eqraz14)
\end{eqnarray}
 
Assim, quando o tamanho da amostra for grande o suficiente para tornar o CV do estimador do total $\widehat{X}$ no denominador da razão $\widehat{R}$ pequeno (digamos, menor que 0,1 ou 10%), então o vício do estimador da razão será pequeno quando comparado com o desvio padrão desse estimador. Vícios desse tipo são geralmente desprezados na prática, a menos que se tenha amostra *muito pequena*.


## Erro quadrático médio de $\widehat{R}$

Como $\widehat{R}$ tem um pequeno vício técnico, a avaliação de sua precisão deve ser feita considerando seu *Erro Quadrático Médio* - *EQM*. Entretanto, sempre que a amostra for grande o suficiente (o que pode ser avaliado calculando o coeficiente de variação da estimativa de total do denominador da razão), o EQM poderá ser bem aproximado pela variância, como indicado:

\begin{eqnarray}
 EQM_p(\widehat{R}) & = & V_p(\widehat{R}) + \left[ B_p( \widehat{R} ) \right]^2 & \doteq & V_p(\widehat{R}) (\#eq:eqraz15)
\end{eqnarray}

já que o termo $\left[ B_p( \widehat{R} ) \right]^2$ fica menor que 1% da variância $V_p(\widehat{R})$ sempre que $CV_p(\widehat{X}) \le 0,1$.

Usando ainda o resultado da Seção \@ref(estoft) quanto à linearização de estimadores que podem ser escritos como funções não lineares de totais, segue-se que podemos aproximar a variância do estimador $\widehat{R}$ pela variância do estimador linearizado, onde a razão depende dos totais populacionais de duas variáveis $(K=2)$, sendo o primeiro definido como $y_{1i} = y_i$ e o segundo $y_{2i} = x_i$, com a função definida como $f(Y_1, Y_2) = Y_1 / Y_2$. 

Nesse caso, a variável linearizada $z_i$ pode ser obtida notando que:

$$
\frac {\partial {f(Y_1, Y_2)}} {\partial{Y_1}} = \frac {1}{Y_2} = \frac {1}{X}
$$

e 
$$
\frac {\partial {f(Y_1, Y_2)}} {\partial{Y_2}} = \frac {-Y_1}{Y^2_2} = \frac {-Y}{X^2}
$$

levando a:
$$
z_i = \frac {1}{X} y_i - \frac {Y}{X^2} x_i = \frac {1}{X} \left( y_i - R x_i \right)
$$

Sendo assim, a variância aproximada do estimador $\widehat{R}$ pode ser obtida calculando a variância do estimador de total da variável linearizada $z_i$:

$$
 V_p ( \widehat{R} ) \doteq V_p(\widehat{Z}_{HT}) = \displaystyle \sum_{i \in U} \sum_{j \in U} \left( \frac{d_i d_j}{d_{ij}} - 1 \right) {z_i} {z_j} (\#eq:eqraz16)
$$

e um estimador dessa variância aproximada é dado por:

$$
\widehat{V}_p ( \widehat{R} ) = \widehat{V}_p(\widehat{Z}_{HT}) = \displaystyle \sum_{i \in s} \sum_{j \in s} \left( {d_i d_j} - {d_{ij}} \right) {z_i} {z_j} (\#eq:eqraz17)
$$

Sob AAS, as expressões acima simplificam para as expressões a seguir. Para mais detalhes, ver @Cochran1977. A variância aproximada do estimador da razão é dada por:

$$
V_{AAS} (\widehat{R}) \doteq \frac{1}{\overline{X}^2} \left( \frac{1}{n} -  \frac{1}{N}\right)  \frac{1}{N-1} \displaystyle \sum_{i \in U} \left( y_i - R x_i \right)^2 (\#eq:eqraz18)
$$

e o estimador da variância fica igual a:

$$
\widehat{V}_{AAS}(\widehat{R}) = \frac{1}{\overline{x}^2}  \left( \frac{1}{n} -  \frac{1}{N}  \right)  \frac{1}{n-1} \displaystyle\sum_{i\in s} \left( y_i - \widehat{R} x_i \right)^2 (\#eq:eqraz19)
$$

A Tabela \@ref(tab:tabrazao2) apresenta os estimadores de uma razão e da respectiva variância sob AAS.

<center>
<table>
<caption>(#tab:tabrazao2)Estimadores de uma razão e respectiva variância sob AAS</caption>
</table>
---------
Estimador                     
---------------------------------------------
$\widehat{R}=\displaystyle\frac{\sum_{i\in s} y_i} {\sum_{i\in s} x_i} = \frac{\overline{y}} {\overline{x}}$
                 
$\widehat{V}_{AAS}(\widehat{R}) =\displaystyle\frac{1}{\overline{x}^2}\left(\frac{1}{n}-\frac{1}{N}\right)\frac{1}{n-1}\displaystyle\sum_{i\in s}\left(y_i-\widehat{R}x_i\right)^2$  

------------
</center>

Antes de fechar este capítulo, vale comentar que a estimação de razões é recorrente em amostragem, pois com frequência é possível usar totais (ou médias) populacionais conhecidos para aprimorar a precisão de estimativas de médias ou totais com base em amostras. O tema da estimação usando informações populacionais auxiliares é tratado no Capítulo \@ref(calib).


**(#exm:exmrazao2)** Estimadores de Razões e Médias de Razões

Considere a população de municípios brasileiros fornecida no arquivo 'MunicBR_dat.rds'.

1.	Selecione uma AAS de $n = 200$ municípios e use esta amostra para estimar os seguintes parâmetros populacionais:
    a. Densidade demográfica média por km<sup>2</sup> no Brasil.
    b. Média da variável densidade demográfica por km<sup>2</sup> por município.
2.	Para cada uma das estimativas acima:
    a.	Estime o erro padrão e o coeficiente de variação. 
    b.	Compare com os correspondentes parâmetros populacionais.
    
3.	Calcule o tamanho da amostra que seria necessário para a estimar densidade demográfica média por km<sup>2</sup> no Brasil com erro máximo de 10 Hab/km<sup>2</sup> com nível de confiança de 95%.
4.	Selecione uma amostra do tamanho calculado em 3 e estime o parâmetro e sua margem de erro, considerando coeficiente de confiança de 95%.

Solução dos itens 1 e 2 do (#exm:exmrazao2), usando R:  


```r
# Limpa área de trabalho
rm(list = ls())

# Carrega biblioteca(s) requerida(s)
library(sampling)
library(tidyverse)
```

```
## Warning: package 'tidyverse' was built under R version 4.1.3
```

```
## -- Attaching packages --------------------------------------- tidyverse 1.3.2 --
## v ggplot2 3.3.6     v purrr   0.3.4
## v tibble  3.1.8     v dplyr   1.0.9
## v tidyr   1.2.0     v stringr 1.4.0
## v readr   2.1.2     v forcats 0.5.1
```

```
## Warning: package 'ggplot2' was built under R version 4.1.3
```

```
## Warning: package 'tibble' was built under R version 4.1.3
```

```
## Warning: package 'dplyr' was built under R version 4.1.3
```

```
## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

```r
# Leitura dos dados
MunicBR_dat <- readRDS(file="Dados/MunicBR_dat.rds")
str(MunicBR_dat)
```

```
## tibble [5,570 x 6] (S3: tbl_df/tbl/data.frame)
##  $ CodMunic : chr [1:5570] "1100015" "1100023" "1100031" "1100049" ...
##  $ SiglaUF  : chr [1:5570] "RO" "RO" "RO" "RO" ...
##  $ CodUF    : chr [1:5570] "11" "11" "11" "11" ...
##  $ Pop      : num [1:5570] 25728 101269 6495 85863 18041 ...
##  $ Area     : num [1:5570] 7067 4427 1314 3793 2783 ...
##  $ Densidade: num [1:5570] 3.64 22.88 4.94 22.64 6.48 ...
```

```r
# Define semente fixa para geração de números aleatórios para permitir repetição
set.seed(123)

# Item 1
# Tamanho da amostra
(n <- 200)
```

```
## [1] 200
```

```r
# Tamanho da população
(N <- nrow(MunicBR_dat))
```

```
## [1] 5570
```

```r
# Seleciona amostra AAS dos municípios
munic_amo <- getdata(MunicBR_dat, srswor(n,N))
str(munic_amo)
```

```
## 'data.frame':	200 obs. of  7 variables:
##  $ ID_unit  : int  41 151 166 185 195 217 277 279 294 316 ...
##  $ CodMunic : chr  "1101435" "1400704" "1501105" "1502202" ...
##  $ SiglaUF  : chr  "RO" "RR" "PA" "PA" ...
##  $ CodUF    : chr  "11" "14" "15" "15" ...
##  $ Pop      : num  7883 9127 26666 65498 13097 ...
##  $ Area     : num  807 8066 4397 615 1431 ...
##  $ Densidade: num  9.77 1.13 6.06 106.55 9.15 ...
```

```r
# Soluções para item 1
# a. Estima densidade demográfica média por km2 no Brasil
(r_chapeu <- munic_amo %>%
             summarise(Popm = mean(Pop),
                       Aream = mean(Area)) %>%
             mutate(Densm = Popm / Aream) %>%
             select(Densm))
```

```
##      Densm
## 1 24.88523
```

```r
# b. Estima média da densidade demográfica por km2 por município
(media.densidade <- munic_amo %>%
                    summarise(Densm = mean(Densidade)))
```

```
##      Densm
## 1 149.7957
```

```r
# Adiciona valor de r_chapeu aos dados da amostra
munic_amo <- cbind(munic_amo, r_chapeu)

# Soluções para item 2
#a.Estima o erro padrão e o coeficiente de variação
(precisao.r_chapeu <- munic_amo %>% 
                     mutate(Z = Pop - Densm * Area) %>%
                     summarise(varZ = var(Z),
                               Aream = mean(Area),
                               Densm = mean(Densm)) %>%
                     mutate(dp.r_chapeu = sqrt((1/n - 1/N)*varZ)/Aream, 
                            cv.r_chapeu = 100 * dp.r_chapeu / Densm)  %>%
                     select(dp.r_chapeu, cv.r_chapeu))
```

```
##   dp.r_chapeu cv.r_chapeu
## 1    3.665081    14.72793
```

```r
(precisao.media.densidade <- munic_amo %>%
         summarise(Densv = var(Densidade),
                   Densm = mean(Densidade)) %>%
         mutate(dp.media.dens = sqrt((1/n - 1/N)*Densv),
                cv.media.dens = 100 * dp.media.dens / Densm) %>%
         select(dp.media.dens, cv.media.dens))
```

```
##   dp.media.dens cv.media.dens
## 1      65.75791      43.89841
```

```r
# b. Calcula densidade demográfica média por km2 no Brasil
(R <- MunicBR_dat %>%
      summarise(Popm = mean(Pop),
                Aream = mean(Area)) %>%
      mutate(Densidade_pop = Popm / Aream) %>%
      select(Densidade_pop))   
```

```
## # A tibble: 1 x 1
##   Densidade_pop
##           <dbl>
## 1          23.6
```

```r
# Estima média da densidade demográfica por km2 por município
(densidade_media_pop <- MunicBR_dat %>%
    summarise(densidade_media_pop = mean(Densidade)))
```

```
## # A tibble: 1 x 1
##   densidade_media_pop
##                 <dbl>
## 1                114.
```

## Exercícios {#exerc6}

**(#exr:exerazao1)** Identifique e defina duas razões que você já tenha utilizado em seu trabalho.

**(#exr:exerazao2)** Numa cidade com 75.000 habitantes,  uma amostra aleatória simples de $n=4$ domicílios foi selecionada dos 25.000 domicílios da cidade para estimar o custo, em Reais, médio de alimentação por domicílio em uma semana. A Tabela \@ref(tab:tabrazao3) mostra os resultados obtidos na amostra.

<center>
<table>
<caption>(#tab:tabrazao3)Informações coletadas na amostra de domicílios</caption>
</table>
----------
 Domicílio   Moradores   Custo dos alimentos (Reais)
----------- ----------- ----------------------------- 
1                   4               150,00

2                   2               100,00

3                   4               200,00

4                   3               140,00

----------
</center>
Considerando que $(N − n)/ N \dot= 1$:

  a) Identifique as unidades de amostragem, a variável de interesse e alguma informação auxiliar associada com as unidades.
  b) Descreva dois tipos de estimadores para estimar a despesa média por domicílio para a alimentação por uma semana na cidade. Sumarize algumas propriedades de cada estimador.
  c) Estime a despesa média por domicílio usando o primeiro estimador e estime a variância do estimador.
  d) Estime a despesa média por domicílio usando o segundo estimador e estime a variância do estimador.
  e) Baseado nos resultados, qual estimador é preferível nesta situação? Por quê?

**(#exr:exerazao3)**  Considere os dados de uma população hipotética.

A Tabela \@ref(tab:tabrazao8) contém os dados dessa população de pesquisa.

<center>
<table>
<caption>(#tab:tabrazao8)População hipotética de $N=9$ unidades</caption>
</table>
----------
 $U_i$	 $X_i$	$Y_i$
------- ------ ------
 1         13     10

 2          7      7

 3         11     13

 4         12     17

 5          4      8

 6          3      1

 7         11     15

 8          3      7

 9          5      4
----------     
</center>

a) Calcule os parâmetros populacionais: $X,\:Y,\:S^2_x,\:S^2_y\:$ e $R$.
b) Determine todas as AAS possíveis de tamanho 3 e construa as distribuições amostrais dos estimadores dos totais, das variâncias e da razão.
c) Construa os histogramas para as distribuições e comente os resultados.
d) Calcule o vício do estimador da razão e compare com o resultado obtido pela fórmula aproximada do vício.


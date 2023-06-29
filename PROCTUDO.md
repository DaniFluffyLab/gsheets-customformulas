# =PROCTUDO(tabela_a_consultar; cabecalho_da_tabela; coluna_a_pesquisar; informacao_a_pesquisar; coluna_a_retornar)

**Descrição:** Fórmula com função parecida do PROCV: ela procura um valor na planilha e retorna outro valor de outra coluna; mas esta procura as informações pelo nome no cabeçalho, e caso o valor procurado apareça mais de uma vez, retorna todos os valores correlacionados, separados por ponto-e-vírgula.

**Marcadores de posição:**
```
tabela_a_consultar
```
```
cabecalho_da_tabela
```
```
coluna_a_pesquisar
```
```
informacao_a_pesquisar
```
```
coluna_a_retornar
```

**Definição da fórmula:**
```
=JOIN("; ";UNIQUE(QUERY(tabela_a_consultar;"select "& SUBSTITUIR(ENDEREÇO(1;CORRESP(coluna_a_retornar;cabecalho_da_tabela;0); 4); 1; "") &" where "& SUBSTITUIR(ENDEREÇO(1;CORRESP(coluna_a_pesquisar;cabecalho_da_tabela;0); 4); 1; "") &"="&SE(TIPO(informacao_a_pesquisar)=2;"'"&informacao_a_pesquisar&"'";informacao_a_pesquisar); FALSO)))
```
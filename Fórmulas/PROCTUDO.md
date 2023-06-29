# =PROCTUDO(tabela_a_consultar; cabecalho_da_tabela; coluna_a_pesquisar; informacao_a_pesquisar; coluna_a_retornar)

**Descrição:** Fórmula com função parecida do PROCV: ela procura um valor na planilha e retorna outro valor de outra coluna; mas caso o valor procurado apareça mais de uma vez, retorna todos os valores correlacionados, separados por ponto-e-vírgula.

**Marcadores de posição:**
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
=JOIN("; "; UNIQUE(FILTER(coluna_a_retornar;coluna_a_pesquisar = informacao_a_pesquisar)))
```

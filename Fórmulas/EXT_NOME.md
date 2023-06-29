# =EXT_NOME(nome_completo)

**Descrição:** Extrai todos os caracteres anteriores ao primeiro espaço da string, sendo comumente usada para separar nome do sobrenome.

**Marcadores de posição:**
```
nome_completo
```

**Definição da fórmula:**
```
=EXT.TEXTO(nome_completo;1;LOCALIZAR(" ";nome_completo;1))
```

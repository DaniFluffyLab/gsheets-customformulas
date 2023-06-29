# =EXT_SOBRENOME(nome_completo)

**Descrição:** Extrai todos os caracteres posteriores ao primeiro espaço da string, sendo comumente usada para separar sobrenome do nome.

**Marcadores de posição:**
```
nome_completo
```

**Definição da fórmula:**
```
=EXT.TEXTO(nome_completo;LOCALIZAR(" ";nome_completo;1)+1;NÚM.CARACT(nome_completo))
```

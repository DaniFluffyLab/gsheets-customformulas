# =CPFCHECK(cpf)

**Descrição:** Valida o CPF, verificando os dois dígitos verificadores. O método de verificação é baseado nesse artigo: [Só Matemática -Cálculo do dígito verificador do CPF](Fórmulas/EXT_SOBRENOME.md)

**Marcadores de posição:**
```
cpf
```

**Definição da fórmula:**
```
=SE(
    ÉNÚM(VALOR(TEXTO(cpf;"00000000000")));SE(
        NÚM.CARACT(TEXTO(cpf;"00000000000"))=11;SE(
            OU(
                TEXTO(cpf;"00000000000")="00000000000";
                TEXTO(cpf;"00000000000")="11111111111";
                TEXTO(cpf;"00000000000")="22222222222";
                TEXTO(cpf;"00000000000")="33333333333";
                TEXTO(cpf;"00000000000")="44444444444";
                TEXTO(cpf;"00000000000")="55555555555";
                TEXTO(cpf;"00000000000")="66666666666";
                TEXTO(cpf;"00000000000")="77777777777";
                TEXTO(cpf;"00000000000")="88888888888";
                TEXTO(cpf;"00000000000")="99999999999"
            )=FALSO;SE(
                DIREITA(
                    MOD((SOMA(
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");1;1)*10);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");2;1)*9);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");3;1)*8);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");4;1)*7);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");5;1)*6);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");6;1)*5);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");7;1)*4);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");8;1)*3);
                        (EXT.TEXTO(TEXTO(cpf;"00000000000");9;1)*2);;
                    )*10);11);1)=(EXT.TEXTO(TEXTO(cpf;"00000000000");10;1));SE(
                    DIREITA(
                        MOD((SOMA(
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");1;1)*11);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");2;1)*10);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");3;1)*9);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");4;1)*8);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");5;1)*7);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");6;1)*6);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");7;1)*5);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");8;1)*4);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");9;1)*3);
                            (EXT.TEXTO(TEXTO(cpf;"00000000000");10;1)*2);
                        )*10);11);1)=(EXT.TEXTO(TEXTO(cpf;"00000000000");11;1));
                        VERDADEIRO;
                    FALSO);
                FALSO);
            FALSO);
        FALSO);
    FALSO
)
```

# =QRCODE(link)

**Descrição:** Insere um QRCode do link informado na célula. Baseado nesta API: https://goqr.me/api/

**Marcadores de posição:**
```
link
```

**Definição da fórmula:**
```
=IMAGE("https://api.qrserver.com/v1/create-qr-code/?size=1000x1000&data="&ENCODEURL(link))
```

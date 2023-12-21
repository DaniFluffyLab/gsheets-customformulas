# =LINKPAGINA(nomeDaPagina)

**Descrição:** Obtém um link que leva diretamente à página na planilha.

**Para uso no Google Apps Script:**
```javascript
/**
 *  Obtém um link que leva diretamente à página na planilha.
 *
 * @param {string} nomeDaPagina
 * @returns {boolean}
 * @customfunction
 */

function LinkPagina(nomeDaPagina) {

    // Se for dado único, executar função
    if (!Array.isArray(nomeDaPagina)) return LinkPagina_(nomeDaPagina)

    // Se array, separar dados e executar função 
    let arrayValue = nomeDaPagina
    let arrayReturn = []
    arrayValue.forEach((row) => {
        let rowReturn = []
        row.forEach((cell) => {
            rowReturn.push(

                // Fórmula a calcular
                LinkPagina_(cell)

            )
        })
        arrayReturn.push(rowReturn)
    })
    return arrayReturn


    // Função a executar
    function LinkPagina_(nome) {
        try {
            return `https://docs.google.com/spreadsheets/d/${SpreadsheetApp.getActiveSpreadsheet().getId()}/edit#gid=${SpreadsheetApp.getActiveSpreadsheet().getSheetByName(nome).getSheetId()}`
        } catch (e) {
            return "Página não encontrada"
        }
    }

}
```

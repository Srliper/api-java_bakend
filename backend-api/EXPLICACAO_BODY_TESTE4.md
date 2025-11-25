# 📝 EXPLICAÇÃO DETALHADA: BODY DO TESTE 4

## 🎯 O QUE É O BODY?

O **Body** é o "corpo" da requisição - são os **dados que você está enviando** para a API atualizar a tarefa.

---

## 💡 POR QUE PRECISA DO BODY NO TESTE 4?

No Teste 4 (PUT), você está **atualizando** uma tarefa existente. Para atualizar, a API precisa saber **quais dados novos** você quer colocar.

**Analogia:**
- É como preencher um formulário
- Você precisa informar os novos valores
- A API vai substituir os dados antigos pelos novos

---

## 📋 BODY DO TESTE 4 - EXPLICAÇÃO LINHA POR LINHA

```json
{
  "nome": "Desenvolvimento da API",
  "dataEntrega": "2025-12-12",
  "responsavel": "Luis 4555952"
}
```

### Linha por Linha:

#### 1. `{` e `}`
- Chaves que delimitam o objeto JSON
- Tudo que está dentro é um objeto JSON

#### 2. `"nome": "Desenvolvimento da API"`
- **Campo:** `nome` (nome da tarefa)
- **Valor:** `"Desenvolvimento da API"`
- **O que faz:** Define o novo nome da tarefa
- **Tipo:** String (texto)

#### 3. `"dataEntrega": "2025-12-12"`
- **Campo:** `dataEntrega` (data de entrega)
- **Valor:** `"2025-12-12"` (formato: ano-mês-dia)
- **O que faz:** Define a nova data de entrega
- **Tipo:** String no formato de data
- **Formato:** `YYYY-MM-DD` (4 dígitos do ano, 2 do mês, 2 do dia)

#### 4. `"responsavel": "Luis 4555952"`
- **Campo:** `responsavel` (responsável pela tarefa)
- **Valor:** `"Luis 4555952"` (seu primeiro nome + RU)
- **O que faz:** Define o novo responsável
- **Tipo:** String (texto)
- **⚠️ IMPORTANTE:** Deve conter seu nome e RU para o trabalho!

#### 5. Vírgulas (`,`)
- Separam os campos
- Último campo não tem vírgula

---

## 🔍 ESTRUTURA DO JSON

```json
{
  "campo1": "valor1",    ← Campo e valor separados por dois pontos (:)
  "campo2": "valor2",    ← Campos separados por vírgula (,)
  "campo3": "valor3"     ← Último campo sem vírgula
}
```

**Regras:**
- ✅ Campos sempre entre aspas duplas `"`
- ✅ Valores de texto entre aspas duplas `"`
- ✅ Campos separados por vírgula `,`
- ✅ Último campo sem vírgula
- ✅ Chaves `{ }` delimitam o objeto

---

## 🎯 POR QUE ESSES CAMPOS ESPECÍFICOS?

Esses campos correspondem à **entidade Tarefa** no código:

```java
public class Tarefa {
    private String nome;           ← "nome"
    private LocalDate dataEntrega; ← "dataEntrega"
    private String responsavel;     ← "responsavel"
}
```

A API espera receber esses 3 campos para atualizar a tarefa.

---

## 📝 COMO CONFIGURAR NO POSTMAN

### Passo a Passo:

1. **Clique na aba "Body"**

2. **Selecione "raw"**
   - Raw = dados brutos (texto puro)

3. **No dropdown à direita, selecione "JSON"**
   - Isso diz ao Postman que você está enviando JSON
   - Postman vai validar a sintaxe

4. **Cole ou digite o JSON:**
   ```json
   {
     "nome": "Desenvolvimento da API",
     "dataEntrega": "2025-12-12",
     "responsavel": "Luis 4555952"
   }
   ```

5. **Verifique:**
   - ✅ Está em formato JSON válido
   - ✅ Todos os campos estão presentes
   - ✅ "Luis 4555952" está correto

---

## ⚠️ ERROS COMUNS NO BODY

### Erro 1: JSON Inválido
```json
{
  "nome": "Desenvolvimento da API",  ← Vírgula no final (errado)
}
```
**Solução:** Remova a vírgula do último campo

### Erro 2: Aspas Erradas
```json
{
  'nome': 'Desenvolvimento da API'  ← Aspas simples (errado)
}
```
**Solução:** Use aspas duplas `"`

### Erro 3: Campo Faltando
```json
{
  "nome": "Desenvolvimento da API"
  ← Faltam "dataEntrega" e "responsavel"
}
```
**Solução:** Inclua todos os 3 campos

### Erro 4: Formato de Data Errado
```json
{
  "dataEntrega": "12/12/2025"  ← Formato errado
}
```
**Solução:** Use formato `YYYY-MM-DD`: `"2025-12-12"`

---

## 🎯 O QUE ACONTECE QUANDO ENVIA O BODY?

1. **Você envia o JSON** no Body
2. **A API recebe** os dados
3. **A API busca** a tarefa pelo ID na URL
4. **A API atualiza** os campos com os novos valores
5. **A API retorna** a tarefa atualizada

**Exemplo:**
- Tarefa antiga: `{"nome": "Tarefa Antiga", ...}`
- Você envia Body: `{"nome": "Desenvolvimento da API", ...}`
- Tarefa atualizada: `{"nome": "Desenvolvimento da API", ...}`

---

## ✅ CHECKLIST DO BODY

Antes de enviar, verifique:

- [ ] Aba "Body" selecionada
- [ ] "raw" selecionado
- [ ] "JSON" selecionado no dropdown
- [ ] JSON válido (sem erros de sintaxe)
- [ ] Campo `"nome"` presente
- [ ] Campo `"dataEntrega"` presente (formato correto)
- [ ] Campo `"responsavel"` presente
- [ ] "Luis 4555952" está correto
- [ ] Vírgulas corretas
- [ ] Aspas duplas em todos os campos

---

## 💡 DICA: VALIDAÇÃO AUTOMÁTICA

O Postman valida o JSON automaticamente:
- ✅ Se estiver correto: texto fica colorido
- ❌ Se tiver erro: aparece mensagem de erro
- ✅ Se selecionar "JSON" no dropdown, o Postman ajuda

---

## 🎯 RESUMO

**Body = Dados que você envia**

**No Teste 4:**
- Body contém os **novos dados** da tarefa
- Formato: **JSON**
- Campos: `nome`, `dataEntrega`, `responsavel`
- **"Luis 4555952"** deve estar no campo `responsavel`

**É como preencher um formulário digital!** 📝

---

**Agora você entende o Body! 🎉**


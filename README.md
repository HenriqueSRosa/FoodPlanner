# **FoodPlanner: Planejador de Refeições e Gerador de Lista de Compras**

Este projeto consiste em uma aplicação para planejar refeições diárias e gerar automaticamente uma lista de compras para a semana. A ferramenta auxilia na organização das refeições, na redução do desperdício de alimentos e na criação de uma lista personalizada de compras com a opção de download em PDF. O aplicativo também oferece suporte ao modo escuro (Dark Mode).

## **Funcionalidades**
- Planejamento de refeições diárias (café da manhã, almoço, lanche e jantar).
- Cálculo das quantidades totais de ingredientes para a semana.
- Geração automática de uma lista de compras.
- Download da lista em PDF.
- Modo escuro (Dark Mode) para melhor conforto visual.

## **Tecnologias Utilizadas**
- HTML, CSS, JavaScript.
- Biblioteca `jsPDF` para exportar a lista de compras em PDF.
- Manipulação do DOM para renderização dinâmica dos dados.

## **Como Usar**

### **1. Adicionar Itens às Refeições**
- Em cada seção de refeições (Café da Manhã, Almoço, Lanche e Jantar), insira o nome do item, quantidade e unidade de medida (gramas, ml, colher de chá, etc.).
- Clique em **Adicionar** para incluir o item na refeição correspondente.
  
### **2. Remover Itens**
- Cada item adicionado aparece em uma lista abaixo do formulário de entrada. Você pode remover itens clicando no botão **Remover** ao lado do respectivo item.

### **3. Gerar Lista de Compras**
- Após adicionar todos os itens, clique em **Gerar Lista de Compras** para ver a lista de todos os ingredientes que você precisará para a semana.
  
### **4. Baixar a Lista de Compras em PDF**
- Uma vez gerada a lista, clique no botão **Baixar Lista de Compras em PDF** para fazer o download da lista de compras no formato PDF.

### **5. Ativar Modo Escuro**
- Para alterar entre os modos claro e escuro, clique no botão **Dark Mode** no topo da página. O botão mudará o texto para **Bright Mode** quando o modo escuro estiver ativado.

## **Estrutura do Código**

### Funções Principais:

1. **`addItem(meal)`**
   - Adiciona itens a uma refeição específica (café da manhã, almoço, lanche ou jantar).
  
2. **`renderList(meal)`**
   - Exibe a lista atual de itens para cada refeição.

3. **`deleteItem(meal, index)`**
   - Remove um item específico de uma refeição.

4. **`generateShoppingList()`**
   - Gera uma tabela com todos os itens de todas as refeições e os exibe.

5. **`downloadPDF(table)`**
   - Gera e baixa um PDF contendo a lista de compras semanal.

6. **`calculateTotalQuantity(quantity, unit)`**
   - Calcula a quantidade total de cada item com base nas refeições da semana.

7. **`toggleDarkMode()`**
   - Alterna entre os modos claro e escuro.

### **Exemplo de Código**
```javascript
function addItem(meal) {
    const item = document.getElementById(`${meal}-item`).value.trim();
    const quantity = parseFloat(document.getElementById(`${meal}-quantity`).value);
    const unit = document.getElementById(`${meal}-unit`).value;

    if (item && !isNaN(quantity)) {
        mealPlans[meal].push({ item, quantity, unit });
        document.getElementById(`${meal}-list`).innerHTML = renderList(meal);
        document.getElementById(`${meal}-item`).value = '';
        document.getElementById(`${meal}-quantity`).value = '';
    }
}

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

```
# Passo a passo para rodar o projeto

## 1. Clonar o Projeto do GitHub

1. **Acesse o repositório no GitHub**:
   - Vá até o repositório no link [aaaaaaa](aaaa.com).
   - Clique no botão verde `Code` e copie o link HTTPS ou SSH do repositório.

2. **Clonar o repositório**:
   - Abra o terminal no seu sistema (PowerShell, CMD ou Git Bash).
   - Navegue até a pasta onde deseja clonar o projeto:
     ```bash
     cd /caminho/da/pasta
     ```
   - Execute o comando de clone usando o link copiado:
     ```bash
     git clone https://github.com/usuario/nome-do-repositorio.git
     ```

## 2. Instalar o VS Code

1. **Baixar o VS Code**:
   - Acesse o site oficial do [Visual Studio Code](https://code.visualstudio.com/).
   - Faça o download da versão correta para o seu sistema operacional (Windows, macOS ou Linux).
   
2. **Instalar o VS Code**:
   - Siga as instruções do instalador para concluir a instalação.
   
3. **Abrir o VS Code**:
   - Após a instalação, abra o VS Code.

## 3. Abrir o Projeto no VS Code

1. **Navegar até a pasta do projeto**:
   - No VS Code, clique em `File` > `Open Folder` (ou `Abrir Pasta` no menu em português).
   - Selecione a pasta onde você clonou o projeto e clique em `Select Folder` (ou `Selecionar Pasta`).

2. **Verificar a estrutura do projeto**:
   - No lado esquerdo, você verá a estrutura de arquivos do projeto, incluindo os arquivos `.html`, `.css` e `.js`.

## 4. Instalar a Extensão Live Server no VS Code

1. **Abrir a aba de Extensões**:
   - No VS Code, clique no ícone de quadrados no lado esquerdo para abrir a aba de Extensões ou use o atalho `Ctrl+Shift+X`.
   
2. **Buscar e instalar o Live Server**:
   - No campo de busca, digite `Live Server`.
   - Clique em `Install` para instalar a extensão `Live Server` desenvolvida por Ritwick Dey.

## 5. Abrir o Projeto Localmente com o Live Server

1. **Executar o Live Server**:
   - Após a instalação, clique com o botão direito do mouse no arquivo `index.html` (ou o arquivo principal HTML do projeto) no explorador de arquivos do VS Code.
   - Selecione a opção `Open with Live Server`.

2. **Acessar o projeto no navegador**:
   - O Live Server abrirá o projeto automaticamente no navegador padrão em um endereço local, como `http://127.0.0.1:5500/`.

3. **Atualizações automáticas**:
   - Com o Live Server rodando, qualquer mudança que você fizer no projeto será refletida automaticamente no navegador.

Pronto! Agora você clonou o projeto, instalou o VS Code e o Live Server, e está com o projeto rodando localmente no seu navegador.

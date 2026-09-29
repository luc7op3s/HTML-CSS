# 🚀 Diário de Estudos & Progresso - HTML5 & CSS3

Repositório de anotações sincronizado entre Desktop e Notebook.

---

## 📌 Status Atual dos Estudos
* **Trilha:** HTML5 e CSS3 (Curso em Vídeo / Gustavo Guanabara)
* **Onde parou:** Módulo 4 — Exercício `Aulas/ex024` (`iframe003.html` concluído)
* **Última Atualização:** 28/09 - 23h20
* **Próximos passos imediatos:**
  1. Segurança em `iframe`: parâmetros `sandbox` e `referrerpolicy` (`iframe004.html`).
  2. Embeds de conteúdo externo (YouTube, Google Maps, etc.) (`iframe005.html` / `iframe006.html`).
  3. Iniciar `ex025` (Formulários HTML).

---

## 📚 Módulo 4: iframes (`ex024`)

### 1. O que é o `<iframe>`
Permite abrir uma "janela" dentro da sua página para carregar outro documento HTML (local ou externo).

### 2. Navegação com Links & iframes (O grande macete do `iframe003.html`)
Para fazer links abrirem **dentro** da mesma janela do iframe sem recarregar a página inteira:
1. No `<iframe>`, dê um atributo `name`:
   ```html
   <iframe name="frame" src="#"></iframe>
   ```
2. Nos links `<a>`, aponte o `target` para o mesmo nome:
   ```html
   <a href="paginas-extras/pagina001.html" target="frame">Primeira Página</a>
   <a href="paginas-extras/pag002.html" target="frame">Segunda Página</a>
   ```

### 3. Fallback de Acessibilidade
Sempre inclua uma mensagem dentro da tag `<iframe>` para navegadores que bloqueiam ou não suportam o recurso:
```html
<iframe src="..." name="...">
    <p>Infelizmente, seu navegador não é compatível.</p>
</iframe>
```

### 4. Organização do Projeto
* Boas práticas: isolar páginas auxiliares em subpastas dedicadas (ex: `paginas-extras/`) para manter o diretório principal limpo.

---

## 🎨 Masterclass de CSS: Resets, Box Model & Viewports

### 1. O Reset Universal Essencial
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /* O pulo do gato! */
}
```
* **Por que zerar `margin` e `padding`?** Elimina os 8px de margem padrão do `body` e os espaçamentos automáticos que cada navegador inventa de fábrica (*User Agent Stylesheet*).
* **O que o `box-sizing: border-box` faz?** Impede que `padding` e `border` aumentem a largura total da caixa. O tamanho declarado se mantém fixo e o espaçamento é empurrado **para dentro**, evitando que o layout estoure no mobile.

### 2. Viewport Units (`vw` e `vh`) vs Porcentagem (`%`)
* **`100%` vs `100vw/100vh`:**
  * `%` é relativo ao **elemento pai** (só estica se o pai tiver tamanho definido).
  * `vw` e `vh` são relativos à **janela inteira do monitor** (*viewport*), independente do pai.
* **Atenção com `100vw` no Desktop:** O `100vw` inclui a largura da barra de rolagem lateral cinza do Windows, o que pode causar uma barra de rolagem horizontal indesejada no rodapé.
* **Cuidado:** Mesmo usando `100vw` ou `100vh`, sem `box-sizing: border-box` qualquer `padding` adicionado vai somar e estourar a tela!

---

## 📊 Módulo 3: Recap Completo de Tabelas (`ex023`)

### 1. Semântica
> **Tabelas servem exclusivamente para dados tabulares.** Nunca usar tabelas para montar layout de sites (layout é trabalho para Flexbox/Grid).

### 2. Estrutura e Hierarquia
```html
<table>
    <caption>Título da Tabela</caption>
    <thead>
        <tr>
            <th scope="col">Coluna 1</th>
            <th scope="col">Coluna 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Dado 1</td>
            <td>Dado 2</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th scope="row">Total</th>
            <td>Soma</td>
        </tr>
    </tfoot>
</table>
```

* `scope="col"`: Título comanda a coluna inteira (acessibilidade).
* `scope="row"`: Título comanda a linha inteira.
* `colspan="N"`: Mescla N colunas na horizontal (elimina `<td>` da linha atual).
* `rowspan="N"`: Mescla N linhas na vertical (elimina `<td>` das linhas de baixo).
* **Mobile:** Envolver em `<div class="tabela-container">` com `overflow-x: auto;` no CSS.

---

## 🛠️ Comandos Diários de Git no Terminal

| Comando | Para que serve | Analogia dos Correios |
| :--- | :--- | :--- |
| `git add .` | Prepara todos os arquivos alterados e criados | Coloca tudo dentro da caixa |
| `git commit -m "mensagem"` | Salva localmente com uma mensagem descritiva | Passa a fita, põe a etiqueta e gera o rastreio |
| `git push` | Envia os commits para o GitHub remoto | Despacha o caminhão dos Correios |
| `git pull` | Baixa as alterações do GitHub para a máquina local | Recebe a encomenda no notebook |
| `git status` | Mostra se há arquivos pendentes para salvar | Olha se a mesa de trabalho tá limpa ou bagunçada |
| `git log --oneline -5` | Mostra os últimos 5 commits de forma limpa e resumida | O histórico de rastreio das últimas entregas |
| `git diff` | Mostra em verde/vermelho o que foi alterado antes de comitar | O raio-X do pacote antes de fechar a caixa |

---

## ⚡ Atalhos Rápidos (VS Code)
* **Mover linha inteira para cima/baixo:** <kbd>Alt</kbd> + <kbd>↑</kbd> ou <kbd>Alt</kbd> + <kbd>↓</kbd> (ótimo para organizar CSS e reorganizar tags sem copiar/colar).

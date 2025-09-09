# Tutorial documentação com MKDocs

Tutorial de como gerar documentação com MKDocs.

## Instruções

1. Instale Python no seu computador (de preferência o [Python Anaconda](https://www.anaconda.com/download));
2. Certifique-se de adicionar o caminho dos binários do Anaconda na variável de ambiente PATH do computador;
3. Abra a linha de comando e instale o MKDocs:

   ```bash
   pip install mkdocs
   ```
   
4. Ainda na linha de comando, crie um novo projeto MKDocs a partir da pasta raiz do seu repositório:
   
   ```bash
   mkdocs new .
   ```
   
5. Será criado um diretório com essa configuração:

   ```
   mkdocs.yml    YAML
   docs/         Folder
   └── index.md  Markdown
   ```

6. Abra o o arquivo `mkdocs.yml` e adicione as extensões para syntax highlighting:
   
   ```yaml
   site_name: Tutorial Documentação com MKDocs
   theme: readthedocs
   markdown_extensions:
     - pymdownx.highlight:
         anchor_linenums: true
         line_spans: __span
         pygments_lang_class: true
     - pymdownx.inlinehilite
     - pymdownx.snippets
     - pymdownx.superfences
   ```

7. Existem dois comandos que podem ser usados agora:
   * `mkdocs serve` (desenvolvimento): inicia um servidor local para visualizar o site. As mudanças feitas na 
     documentação são refletidas no site.
   * `mkdocs build` (produção): gera as páginas em HTML.

   Vamos usar o comando `mkdocs serve` para visualizar o site:

   ```bash
   mkdocs serve
   ```

8. Abra o navegador e acesse [http://127.0.0.1:8000](http://127.0.0.1:8000)
9. Altere o texto do arquivo `docs/index.md` e salve. Visualize novamente na URL [http://127.0.0.1:8000](http://127.0.0.1:8000) 
10. Existem muitas configurações que podem ser feitas a partir de agora: alterar o título do site, o tema, adicionar mais 
    páginas, dentre outros. Consulte a documentação oficial do MKDocs[^1] para mais informações.
11. Quando terminar, construa as páginas HTML com 
    
    ```bash
    mkdocs build
    ```

12. Salve o conteúdo do repositório no GitHub:
    
    ```bash
    git add .
    git commit -m "adicionada documentação com MKDocs"
    git push origin main
    ```


# Recursos adicionais

[^1]: [Tutorial MKDocs](https://www.mkdocs.org/getting-started)
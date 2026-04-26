# SETUP.md — Passo a passo completo

## 1. Criar o repositório no GitHub

1. Acesse https://github.com/new
2. Nome: `graph-search-complexity`
3. Visibilidade: **Public** (obrigatório para GitHub Pages grátis)
4. NÃO inicialize com README (você vai subir a estrutura pronta)
5. Clique em "Create repository"

---

## 2. Clonar e subir a estrutura

```bash
# Clone o repo vazio
git clone https://github.com/SEU_USUARIO/graph-search-complexity
cd graph-search-complexity

# Copie todos os arquivos deste setup para dentro da pasta
# (ou crie manualmente conforme estrutura do README)

# Primeiro commit
git add .
git commit -m "feat: estrutura inicial do projeto e configuração do blog"
git push origin main
```

---

## 3. Ativar GitHub Pages

1. No repositório, vá em **Settings** → **Pages**
2. Em "Source", selecione **GitHub Actions**
3. Salve

O deploy acontece automaticamente a cada push na branch `main`.
A URL do blog será: `https://SEU_USUARIO.github.io/graph-search-complexity`

---

## 4. Substituir "seu-usuario" nos arquivos

Antes do primeiro push, substitua nos arquivos:

- `mkdocs.yml` → `site_url`, `repo_url`, link do Twitter
- `README.md` → badge de deploy, URL do blog
- `docs/index.md` → bloco de código de clone

```bash
# Atalho para substituir tudo de uma vez (Linux/macOS)
grep -rl "seu-usuario" . | xargs sed -i 's/seu-usuario/SEU_USUARIO_REAL/g'
```

---

## 5. Estrutura de commits recomendada

Cada etapa da pesquisa vira um commit descritivo:

```
feat: implementação do gerador de grafo Erdős–Rényi
feat: implementação do BFS com instrumentação de métricas
feat: pipeline de experimentos para grafos esparsos
data: resultados experimento BFS × grade 1000 nós
docs: análise do gap BFS vs teoria
```

Isso cria um diário de pesquisa público com datas, citável no artigo.

---

## 6. Rodar o blog localmente antes de subir

```bash
pip install -r requirements-docs.txt
mkdocs serve
```

Acesse `http://127.0.0.1:8000` e veja o blog antes de publicar.

---

## 7. Verificar deploy

Após o push, vá em **Actions** no GitHub e acompanhe o workflow `Deploy MkDocs to GitHub Pages`.
Em ~2 minutos o blog estará no ar.

# SUAP — Relatório de Projetos em Execução

Sistema web para geração de relatórios de projetos em execução do SUAP/IFPI.
Permite login, visualização de projetos e exportação para Excel — tudo pelo navegador.

---

## Pré-requisitos

- Python 3.9 ou superior instalado
- Acesso à internet (para acessar o SUAP)

---

## Instalação (primeira vez)

### 1. Abra o terminal/prompt de comando na pasta do projeto

### 2. (Opcional, recomendado) Crie um ambiente virtual
```bash
python -m venv venv
```
Ative o ambiente:
- **Windows:** `venv\Scripts\activate`
- **Mac/Linux:** `source venv/bin/activate`

### 3. Instale as dependências
```bash
pip install -r requirements.txt
```

---

## Executando o sistema

```bash
python app.py
```

Acesse no navegador: **http://localhost:5000**

---

## Como usar

1. **Login** — Informe seu usuário e senha do SUAP. A validação é feita diretamente no SUAP.
2. **Buscar projetos** — Escolha o ano (2017–2026) e clique em "Buscar Projetos".
   - Os projetos aparecem na tabela conforme são carregados.
   - As pendências e metas são buscadas projeto a projeto (pode levar alguns minutos).
3. **Filtrar** — Use o campo de busca para filtrar por nome ou coordenador.
4. **Exportar** — Clique em "Exportar Excel" para baixar o relatório formatado.

---

## Estrutura de arquivos

```
projeto/
├── app.py              ← Servidor Flask (backend)
├── requirements.txt    ← Dependências Python
├── README.md           ← Este arquivo
└── templates/
    └── index.html      ← Interface web (frontend)
```

---

## Observações

- As sessões são mantidas em memória. Se o servidor reiniciar, será necessário fazer login novamente.
- Para uso em produção (múltiplos usuários simultâneos), recomenda-se usar Gunicorn ou similar.
- O sistema acessa o painel administrativo do SUAP, portanto requer uma conta com as permissões adequadas.
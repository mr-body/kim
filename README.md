# kim

Jogo feito na **Godot Engine**.

## Sumário

- [Visão geral](#visão-geral)
- [Tecnologias](#tecnologias)
- [Como abrir e rodar o projeto](#como-abrir-e-rodar-o-projeto)
- [Export (build)](#export-build)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Padrões e boas práticas](#padrões-e-boas-práticas)
- [Arte, áudio e direitos](#arte-áudio-e-direitos)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

## Visão geral

O **kim** é um jogo desenvolvido com a **Godot Engine**.

Este README tem como objetivo documentar:

- como abrir o projeto localmente;
- como rodar e depurar;
- como exportar builds;
- organização sugerida e práticas para contribuir.

> Se você me disser a versão exata da Godot (ex.: 4.2, 4.3, 3.5) eu ajusto as instruções de export, inputs e pastas para bater 100% com a versão.

## Tecnologias

- **Godot Engine** (projeto de jogo)
- **GDScript** (provável, dependendo do projeto)

## Como abrir e rodar o projeto

### 1) Pré-requisitos

- Instalar a **Godot Engine** compatível com o projeto.
- Git instalado (opcional, se você for clonar o repositório).

### 2) Clonar o repositório

```bash
git clone https://github.com/mr-body/kim.git
cd kim
```

### 3) Abrir no Godot

1. Abra a Godot
2. Clique em **Import** (ou **Scan**, dependendo da versão)
3. Selecione a pasta do repositório `kim/`
4. Abra o projeto e aguarde o import de assets

### 4) Rodar o jogo

- Clique no botão **Play** (F5) para rodar o projeto.
- Use **Play Current Scene** (F6) para rodar a cena atual.

## Export (build)

> O fluxo pode variar um pouco entre Godot 3.x e 4.x, mas em geral é:

1. Abra o projeto
2. Vá em **Project → Export...**
3. Adicione um preset (Windows / Linux / macOS / Web)
4. Instale os **Export Templates** quando solicitado
5. Configure:
   - Nome do executável
   - Ícone
   - Arquivos incluídos/ignorados
6. Clique em **Export Project**

### Export para Web (HTML5)

- Crie um preset de **Web**
- Exporte para uma pasta, por exemplo `dist/web/`

> Dica: se você pretende publicar no GitHub Pages, é comum exportar para `docs/` ou para uma pasta que o workflow copie para Pages.

## Estrutura do repositório

A estrutura exata depende do projeto, mas em projetos Godot normalmente você verá algo como:

- `project.godot` (arquivo principal do projeto)
- `*.tscn` (cenas)
- `*.gd` (scripts)
- `assets/` (sprites, fontes, sons)

Se quiser, eu posso mapear a estrutura real do repositório e documentar aqui (ex.: cena inicial, pastas de UI, player, inimigos etc.).

## Padrões e boas práticas

### Convenções de nomes

Sugestão (ajuste à sua preferência):

- Cenas: `PascalCase.tscn` (ex.: `MainMenu.tscn`, `Level01.tscn`)
- Scripts: `snake_case.gd` ou `PascalCase.gd` (mantenha consistente)
- Assets: `snake_case` e pastas por categoria (`sprites/`, `sfx/`, `music/`)

### Organização

- Evite cenas “gigantes”: prefira cenas pequenas e composáveis.
- Use autoloads/singletons apenas quando fizer sentido.
- Centralize configs (ex.: `GameConfig`, `Settings`) e documente.

### Salvamento/config

Se o jogo salvar progresso/configurações:

- documente onde salva (ex.: `user://savegame.dat`)
- documente formato (JSON/binário) e versão

## Arte, áudio e direitos

Defina aqui a origem dos assets:

- Assets originais?
- Assets de terceiros? (com licença e atribuição)

Sugestão: criar uma pasta `credits/` ou `docs/credits.md` listando:

- autor
- link
- licença

## Troubleshooting

### O projeto não importa / dá erro ao abrir

- Confirme se está usando a **mesma versão da Godot** usada para criar o projeto.
- Se for Godot 4.x, abrir em 3.x normalmente quebra (e vice-versa).

### Texturas/som não aparecem

- Verifique se os arquivos estão versionados no Git (não ignorados por `.gitignore`).
- Confirme caminhos de import e se os assets foram reimportados.

### Export falha

- Instale os **Export Templates** (Editor vai indicar).
- Confira permissões de escrita na pasta de destino.

## Roadmap

- [ ] Definir versão alvo da Godot
- [ ] Documentar cena inicial (entrypoint)
- [ ] Criar pipeline de build/export (opcional)
- [ ] Adicionar créditos/licenças de assets

## Contribuindo

1. Faça um fork do repositório
2. Crie uma branch:

```bash
git checkout -b feat/minha-melhoria
```

3. Faça commits descritivos:

```bash
git commit -m "feat: adiciona movimento do player"
```

4. Abra um Pull Request descrevendo:

- o que foi alterado
- como testar
- prints/gifs (se for mudança visual)

## Licença

Ainda não definido.

Se você quiser, eu posso:

- adicionar uma licença (MIT, Apache-2.0, GPL-3.0 etc.), ou
- deixar explícito o status de direitos autorais.

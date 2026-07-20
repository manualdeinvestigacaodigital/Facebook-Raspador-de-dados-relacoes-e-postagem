<p align="center">
  <img src="https://raw.githubusercontent.com/manualdeinvestigacaodigital/facebook-raspador-de-dados-web-scraper/main/Face.png" width="140" alt="Raspador de dados do Facebook">
</p>

<h1 align="center">🔎 Raspador de Dados de Relações e Postagens do Facebook</h1>

<p align="center">
  Extensão Chrome para coleta estruturada, documentação e preservação de dados disponibilizados pelo Facebook ao navegador.
</p>

<p align="center">
  <strong>✅ Versão estável: 44.21.28</strong><br>
  Desenvolvida por <strong>Guilherme Caselli</strong>
</p>

---

## 📌 Visão geral

O **Raspador de Dados de Relações e Postagens do Facebook** é uma extensão para Google Chrome e navegadores baseados em Chromium, construída em **Manifest V3**, destinada à coleta estruturada de informações disponibilizadas ao navegador durante a navegação no Facebook.

A ferramenta foi desenvolvida para apoiar atividades de:

- 🕵️ investigação digital;
- 🧠 inteligência;
- 🌐 OSINT;
- 🧾 documentação técnica;
- 🗂️ preservação de conteúdo;
- 📊 análise de dados públicos ou legitimamente acessíveis;
- 🔐 organização e verificação de evidências digitais;
- 📑 geração de relatórios estruturados.

A extensão utiliza somente os elementos, estruturas, atributos, hyperlinks, identificadores, mídias e respostas entregues pelo Facebook ao navegador durante a sessão do usuário.

> ⚠️ A ferramenta não cria, presume nem completa informações ausentes.

Quando o Facebook não materializa todo o conteúdo declarado, o resultado é apresentado como **parcial seguro**, diferenciando:

- quantidade declarada;
- quantidade observada;
- quantidade exportada;
- motivo de encerramento.

---

## 🖥️ Interface principal

<p align="center">
  <img src="imagens/01-painel-inicial.png" width="520" alt="Painel inicial da ferramenta">
</p>

O painel apresenta dois fluxos principais:

- 👥 **Coletar relações selecionadas**
- 📝 **Postagem aberta**

Também é possível marcar:

```text
Raspar interações
```

Essa opção inclui na coleta os perfis efetivamente materializados pelo Facebook nos grupos de reação.

---

## 👥 Relações de perfil

A versão estável permite coletar, quando disponibilizadas:

- 👤 Amigos
- ➡️ Seguindo
- ⬅️ Seguidores

As relações são tratadas separadamente. A ferramenta não apresenta perfis de **Seguindo** como **Amigos** e não converte **Seguidores** em outra categoria.

### ⚙️ Funcionamento do motor relacional

O motor:

- identifica a subguia interna materializada;
- delimita a coleção nominal correspondente;
- percorre a lista progressivamente;
- preserva registros durante a reciclagem do DOM;
- deduplica perfis;
- mantém a URL inalterada;
- não atualiza a página automaticamente;
- não aciona subguias por cliques sintéticos;
- não utiliza busca alfabética como substituto da coleção;
- não utiliza `/friends_all` como atalho;
- não captura cartões de Photos, Reels, Check-ins ou Reviews;
- encerra ao confirmar o final estrutural da coleção;
- registra relações não disponibilizadas sem inventar dados.

### 📋 Dados que podem ser preservados

- nome;
- URL do perfil;
- avatar;
- identificadores observados;
- tipo de relação;
- dados exibidos no cartão;
- origem da observação;
- data e hora da coleta.

---

## 📝 Postagens tradicionais

Em publicações do tipo POST, a ferramenta pode preservar:

- 👤 autor;
- 🔗 URL do autor;
- 🖼️ avatar;
- 📝 texto ou legenda;
- 🔗 URL original;
- 📅 data;
- 🌐 privacidade ou visibilidade;
- 📍 local;
- 👥 pessoas marcadas;
- 🔗 entidades e hyperlinks;
- 📊 métricas;
- 💬 comentários;
- ↩️ respostas;
- 😀 reações;
- 🎞️ mídias associadas.

---

## 🖼️ Fotografias

No visualizador de fotos, a extensão pode coletar:

- fotografia principal;
- autor e avatar;
- legenda;
- data;
- local;
- privacidade;
- álbum;
- comentários;
- respostas;
- reações;
- hyperlinks;
- métricas observadas.

A coleta permanece vinculada à fotografia aberta.

---

## 🎬 Reels e vídeos

Para Reels e vídeos, a ferramenta utiliza vínculo técnico entre a mídia e o conteúdo ativo.

### 🚫 São rejeitados

- vídeos pertencentes a outro Reel;
- mídias carregadas em segundo plano;
- recomendações adjacentes;
- conteúdo pertencente a rota anterior;
- candidatos sem vínculo com a publicação ativa;
- imagens incorretamente apresentadas como vídeo.

### ▶️ Quando o vídeo está disponível

Quando o Facebook fornece uma URL HTTP(S) reutilizável e comprovadamente vinculada ao vídeo, o HTML pode apresentar:

- player de vídeo;
- link para abrir o vídeo completo;
- opção de download, sujeita às permissões do navegador e do servidor.

Quando uma URL reutilizável não está disponível, o relatório preserva o poster correto e registra a limitação.

---

## 💬 Comentários e respostas

A ferramenta tenta:

- selecionar **Todos os comentários**;
- expandir respostas;
- percorrer progressivamente o painel;
- deduplicar registros;
- preservar a hierarquia;
- manter hyperlinks;
- manter avatares;
- preservar stickers, GIFs e mídias anexadas.

Para cada comentário ou resposta podem ser registrados:

- autor;
- URL do perfil;
- avatar;
- texto;
- mídia;
- figurinha ou GIF;
- número de curtidas;
- data;
- identificador técnico;
- vínculo com o comentário principal;
- hyperlink para o comentário.

---

## 😀 Interações e reações

Com a opção abaixo marcada:

```text
Raspar interações
```

a ferramenta tenta coletar os perfis materializados pelo Facebook nas categorias:

- 👍 Curtir
- ❤️ Amei
- 🥰 Força
- 😂 Haha
- 😮 Uau
- 😢 Triste
- 😡 Grr

Os resultados podem conter:

- nome;
- URL;
- avatar;
- resolução do avatar;
- tipo de reação;
- quantidade declarada;
- quantidade de perfis observados.

<p align="center">
  <img src="imagens/04-interacoes-anonimizadas.png" width="520" alt="Exemplo anonimizado de interações">
</p>

> 🔒 As imagens demonstrativas podem conter dados fictícios ou anonimizados.

---

## 📦 Exportações

A ferramenta permite selecionar individualmente:

- 📄 HTML
- 📑 PDF
- 🧾 JSON
- 📊 Excel XLSX
- 📋 CSV

<p align="center">
  <img src="imagens/02-formatos-exportacao.png" width="520" alt="Seleção de formatos de exportação">
</p>

O painel apresenta os comandos:

```text
Marcar todos
Limpar
Baixar selecionados
Cancelar
```

Cada formato é gerado somente após ação expressa do usuário.

---

## 📊 Relatório estruturado

O relatório HTML pode organizar:

- autor;
- avatar;
- legenda;
- métricas;
- metadados;
- mídia principal;
- comentários;
- respostas;
- interações;
- hyperlinks;
- status da coleta;
- data e hora do export.

<p align="center">
  <img src="imagens/03-relatorio-postagem.png" width="520" alt="Exemplo de relatório estruturado">
</p>

---

## 🔐 Integridade dos artefatos

Cada arquivo exportado é acompanhado por um **Laudo de Integridade em PDF**.

O laudo registra:

- data e hora;
- URL de origem;
- nome do arquivo;
- formato;
- tamanho;
- hash SHA-256;
- hash SHA-512;
- status do export;
- identificação da ferramenta.

Exemplo de campos:

```text
Data/Hora
URL de origem
Nome do arquivo
Formato
Tamanho
SHA-256
SHA-512
Status do export
```

Os hashes permitem verificar posteriormente se o artefato permaneceu inalterado.

---

## ✅ Requisitos

- Google Chrome ou navegador Chromium;
- permissão para carregar extensões em modo desenvolvedor;
- acesso ao Facebook;
- sessão autenticada, quando necessária;
- conexão estável;
- página corretamente carregada.

---

## 📥 Download da ferramenta

### Opção 1 — Download direto pelo GitHub

Acesse:

```text
https://github.com/manualdeinvestigacaodigital/Facebook-Raspador-de-dados-relacoes-e-postagem
```

Depois:

1. clique em **Code**;
2. escolha **Download ZIP**;
3. extraia o conteúdo;
4. confirme que `manifest.json` está diretamente na pasta extraída.

### Opção 2 — Download com Git

Copie e execute:

```bash
git clone https://github.com/manualdeinvestigacaodigital/Facebook-Raspador-de-dados-relacoes-e-postagem.git
cd Facebook-Raspador-de-dados-relacoes-e-postagem
```

Para verificar se o Git está instalado:

```bash
git --version
```

---

## 🧩 Instalação no Google Chrome

1. Abra:

```text
chrome://extensions/
```

2. Ative:

```text
Modo do desenvolvedor
```

3. Clique em:

```text
Carregar sem compactação
```

4. Selecione a pasta que contém diretamente:

```text
manifest.json
```

5. Confirme no painel:

```text
versão ativa 44.21.28
```

> ⚠️ Não selecione o ZIP. A extensão deve ser carregada a partir da pasta extraída.

---

## 🚀 Uso básico

### 👥 Coleta de relações

1. abra o perfil;
2. acesse a área de relações;
3. deixe visível a subguia desejada;
4. abra o painel da extensão;
5. selecione **Todas**, **Amigos**, **Seguindo** ou **Seguidores**;
6. clique em:

```text
Coletar relações selecionadas
```

7. aguarde o encerramento;
8. selecione os formatos de exportação.

### 📝 Coleta de postagem, foto, Reel ou vídeo

1. abra diretamente o conteúdo;
2. aguarde o carregamento;
3. abra o painel;
4. marque, quando necessário:

```text
Raspar interações
```

5. clique em:

```text
Postagem aberta
```

6. aguarde a conclusão;
7. confira as quantidades declarada e observada;
8. selecione os formatos.

---

## 🗂️ Estrutura do projeto

```text
Facebook-Raspador-de-dados-relacoes-e-postagem/
├── manifest.json
├── README.md
├── content.js
├── exact_relation_collector_442127.js
├── main_world_hook.js
├── post_comment_bridge.js
├── post_comment_main_hook.js
├── post_reaction_bridge.js
├── post_reaction_main_hook.js
├── post_scraper_module.js
├── reel_evidence_bridge.js
├── reel_evidence_main_hook.js
├── service_worker.js
├── unified_controller.js
├── unified_preflight.js
└── imagens/
    ├── 01-painel-inicial.png
    ├── 02-formatos-exportacao.png
    ├── 03-relatorio-postagem.png
    └── 04-interacoes-anonimizadas.png
```

---

## 🧠 Responsabilidade dos módulos

- `manifest.json` — manifesto, permissões e ordem de carregamento.
- `content.js` — núcleo de coleta e estruturas compartilhadas.
- `exact_relation_collector_442127.js` — coleta delimitada de relações.
- `main_world_hook.js` — integração controlada com o contexto principal.
- `post_comment_bridge.js` — transporte de dados de comentários.
- `post_comment_main_hook.js` — observação das estruturas de comentários.
- `post_reaction_bridge.js` — transporte dos dados de reações.
- `post_reaction_main_hook.js` — observação das interações.
- `post_scraper_module.js` — coleta e composição de postagens, fotos e mídias.
- `reel_evidence_bridge.js` — transporte de evidências de Reel.
- `reel_evidence_main_hook.js` — vínculo da mídia ao Reel ativo.
- `service_worker.js` — ciclo de vida Manifest V3.
- `unified_controller.js` — painel, coordenação e exportações.
- `unified_preflight.js` — validação do contexto antes da execução.

---

## 🛡️ Princípios técnicos

A versão estável foi estruturada para:

- vincular a coleta ao conteúdo ativo;
- preservar POST, PHOTO, VIDEO e REEL;
- separar Amigos, Seguindo e Seguidores;
- impedir refresh e navegação automática no fluxo relacional;
- preservar registros durante a reciclagem do DOM;
- deduplicar perfis, comentários, respostas e interações;
- manter a hierarquia dos comentários;
- impedir associação incorreta de avatares;
- rejeitar mídia pertencente a outro Reel;
- separar quantidade declarada, observada e exportada;
- registrar resultados parciais;
- gerar hashes e laudos por artefato;
- funcionar em Manifest V3.

---

## ⚠️ Limitações

O funcionamento depende das estruturas entregues pelo Facebook e pode ser afetado por:

- mudanças no DOM;
- alterações de seletores;
- carregamento progressivo;
- virtualização e reciclagem de elementos;
- filtros de comentários;
- privacidade;
- conteúdo não materializado;
- reações sem nomes;
- comentários excluídos ou moderados;
- instabilidade de rede;
- limites de sessão;
- mídia por `blob:`;
- MSE ou DASH;
- expiração de URLs temporárias;
- alterações internas da plataforma.

> ⚠️ Resultado parcial não deve ser tratado como coleta completa.

---

## 🔒 Segurança, privacidade e uso responsável

A utilização deve observar:

- legislação aplicável;
- finalidade legítima;
- necessidade;
- proporcionalidade;
- proteção de dados;
- sigilo;
- controle de acesso;
- cadeia de custódia;
- políticas da plataforma.

O usuário é responsável pela base legal da coleta e pelo tratamento das informações obtidas.

Este projeto não possui vínculo oficial com o Facebook ou com a Meta.

---

## 👤 Autor

**Guilherme Caselli**  
Delegado de Polícia  
Professor da Academia de Polícia de São Paulo  
Autor de *Manual de Investigação Digital* — Editora Juspodivm

Instagram:

```text
https://instagram.com/guilhermecaselli
```

Página do autor:

```text
https://www.editorajuspodivm.com.br/authors/page/view/id/206/
```

<p align="center">
  <img src="https://raw.githubusercontent.com/manualdeinvestigacaodigital/facebook-raspador-de-dados-web-scraper/main/Face.png" width="140" alt="Raspador de dados do Facebook">
</p>

<h1 align="center">Raspador de Dados de Relações e Postagens do Facebook</h1>

<p align="center">
  Extensão Chrome para coleta estruturada, documentação e preservação de dados disponibilizados pelo Facebook ao navegador.
</p>

<p align="center">
  <strong>Versão estável: 44.21.28</strong><br>
  Desenvolvida por <strong>Guilherme Caselli</strong>
</p>

---

## Visão geral

O **Raspador de Dados de Relações e Postagens do Facebook** é uma extensão para Google Chrome e navegadores baseados em Chromium, construída em **Manifest V3**, destinada à coleta estruturada de informações disponibilizadas ao navegador durante a navegação no Facebook.

A ferramenta foi desenvolvida para apoiar atividades de:

- investigação digital;
- inteligência;
- OSINT;
- documentação técnica;
- preservação de conteúdo;
- análise de dados públicos ou legitimamente acessíveis à sessão autenticada;
- organização de evidências digitais;
- geração de relatórios estruturados;
- verificação de integridade dos artefatos exportados.

A extensão trabalha com os elementos visíveis, estruturas DOM, atributos acessíveis, hyperlinks, identificadores de rota, elementos de mídia e respostas entregues pelo Facebook ao navegador. A ferramenta não cria, presume ou completa informações ausentes.

Quando o Facebook não materializa todo o conteúdo declarado, o resultado é apresentado como **parcial seguro**, distinguindo:

- quantidade declarada;
- quantidade efetivamente observada;
- quantidade exportada;
- motivo de encerramento da coleta.

---

## Interface principal

<p align="center">
  <img src="imagens/01-painel-inicial.png" width="900" alt="Painel inicial da ferramenta">
</p>

O painel reúne dois fluxos principais:

- **Coletar relações selecionadas**
- **Postagem aberta**

Também permite marcar **Raspar interações**, incluindo na mesma coleta os perfis materializados pelo Facebook nos grupos de reação.

---

## Funcionalidades

### Relações de perfil

A versão estável permite coletar, quando disponibilizadas pelo Facebook:

- **Amigos**
- **Seguindo**
- **Seguidores**

As relações são tratadas separadamente. A ferramenta não apresenta perfis de **Seguindo** como **Amigos** e não converte **Seguidores** em outra categoria.

O motor relacional:

- identifica a subguia interna realmente materializada;
- delimita a coleção nominal correspondente;
- percorre a lista progressivamente;
- acumula os registros mesmo quando o Facebook recicla elementos do DOM;
- deduplica perfis;
- mantém a URL inalterada;
- não atualiza a página automaticamente;
- não aciona subguias por cliques sintéticos;
- não usa busca alfabética como substituto da coleção;
- não utiliza `/friends_all` como atalho;
- não captura cartões de Photos, Reels, Check-ins, Reviews ou outras seções externas;
- encerra ao confirmar o final estrutural da coleção;
- registra relações não materializadas sem inventar registros.

Para cada perfil podem ser preservados, quando observados:

- nome;
- URL;
- avatar;
- identificadores;
- relação;
- dados exibidos no cartão;
- origem da observação;
- data e hora da coleta.

---

### Postagens tradicionais

Em publicações do tipo POST, a ferramenta pode preservar:

- autor;
- URL do autor;
- avatar;
- texto ou legenda;
- URL original;
- data;
- privacidade ou visibilidade;
- local;
- pessoas marcadas;
- entidades e hyperlinks;
- métricas;
- comentários;
- respostas;
- reações;
- mídias associadas.

---

### Fotografias

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

### Reels e vídeos

Para Reels e vídeos, a ferramenta utiliza vínculo técnico entre a mídia e o conteúdo ativo.

São rejeitados:

- vídeos pertencentes a outro Reel;
- mídias carregadas em segundo plano;
- recomendações adjacentes;
- conteúdo pertencente a uma rota anterior;
- candidatos sem vínculo com a publicação ativa;
- imagens apresentadas incorretamente como vídeo.

Quando o Facebook fornece uma URL HTTP(S) reutilizável e comprovadamente vinculada ao vídeo, o HTML pode apresentar:

- player de vídeo;
- link para abrir o vídeo completo;
- opção de download, sujeita às permissões do navegador e do servidor de origem.

Quando uma URL reutilizável não está disponível, o relatório preserva o poster correto e registra a limitação.

---

### Comentários e respostas

A ferramenta tenta:

- selecionar **Todos os comentários**, quando disponível;
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

### Interações e reações

Com **Raspar interações** marcado, a ferramenta tenta coletar os perfis materializados pelo Facebook nas categorias:

- Curtir;
- Amei;
- Força;
- Haha;
- Uau;
- Triste;
- Grr.

Os resultados podem conter:

- nome;
- URL;
- avatar;
- resolução do avatar;
- tipo de reação;
- quantidade declarada;
- quantidade de perfis efetivamente observados.

<p align="center">
  <img src="imagens/04-interacoes-anonimizadas.png" width="900" alt="Exemplo anonimizado de interações">
</p>

> As imagens demonstrativas podem conter dados fictícios ou anonimizados.

---

## Exportações

A ferramenta permite selecionar individualmente:

- **HTML**
- **PDF**
- **JSON**
- **Excel XLSX**
- **CSV**

<p align="center">
  <img src="imagens/02-formatos-exportacao.png" width="900" alt="Seleção de formatos de exportação">
</p>

O painel de exportação apresenta:

- **Marcar todos**
- **Limpar**
- **Baixar selecionados**
- **Cancelar**

Cada formato é gerado somente após ação expressa do usuário.

---

## Relatório estruturado

O relatório HTML organiza visualmente:

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
  <img src="imagens/03-relatorio-postagem.png" width="900" alt="Exemplo de relatório estruturado">
</p>

---

## Integridade dos artefatos

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

Os hashes permitem verificar posteriormente se o artefato permaneceu inalterado.

---

## Requisitos

- Google Chrome ou navegador Chromium;
- permissão para carregar extensões em modo desenvolvedor;
- acesso ao Facebook;
- sessão autenticada, quando necessária;
- conexão estável;
- página de perfil, postagem, foto, vídeo ou Reel corretamente carregada.

---

## Instalação

### Download pelo GitHub

1. Acesse:

   `https://github.com/manualdeinvestigacaodigital/Facebook-Raspador-de-dados-relacoes-e-postagem`

2. Clique em **Code**.
3. Escolha **Download ZIP**.
4. Extraia o conteúdo.
5. Confirme que `manifest.json` está diretamente na pasta extraída.

### Download com Git

```bash
git clone https://github.com/manualdeinvestigacaodigital/Facebook-Raspador-de-dados-relacoes-e-postagem.git
cd Facebook-Raspador-de-dados-relacoes-e-postagem
```

### Carregamento no Chrome

1. Abra `chrome://extensions/`.
2. Ative **Modo do desenvolvedor**.
3. Clique em **Carregar sem compactação**.
4. Selecione a pasta que contém diretamente `manifest.json`.
5. Confirme no painel:

```text
versão ativa 44.21.28
```

Não selecione o ZIP. A extensão deve ser carregada a partir da pasta extraída.

---

## Uso básico

### Relações

1. Abra o perfil.
2. Acesse a área de relações.
3. Deixe visível a subguia desejada.
4. Abra o painel da extensão.
5. Selecione **Todas**, **Amigos**, **Seguindo** ou **Seguidores**.
6. Clique em **Coletar relações selecionadas**.
7. Aguarde o encerramento.
8. Selecione os formatos de exportação.

### Postagem, foto, Reel ou vídeo

1. Abra diretamente o conteúdo.
2. Aguarde o carregamento.
3. Abra o painel.
4. Marque **Raspar interações**, quando necessário.
5. Clique em **Postagem aberta**.
6. Aguarde a conclusão.
7. Confira as quantidades declarada e observada.
8. Selecione os formatos.

---

## Estrutura do projeto

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

### Módulos

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
- `service_worker.js` — ciclo de vida da extensão Manifest V3.
- `unified_controller.js` — painel, coordenação e exportações.
- `unified_preflight.js` — validação do contexto antes da execução.

---

## Princípios técnicos

A versão estável foi estruturada para:

- vincular a coleta ao conteúdo ativo;
- preservar POST, PHOTO, VIDEO e REEL;
- separar Amigos, Seguindo e Seguidores;
- impedir refresh e navegação automática no fluxo relacional;
- preservar registros durante a reciclagem do DOM;
- deduplicar perfis, comentários, respostas e interações;
- manter a hierarquia dos comentários;
- impedir associação incorreta de avatares;
- rejeitar mídia de outro Reel;
- separar quantidade declarada, observada e exportada;
- registrar resultados parciais de forma explícita;
- gerar hashes e laudos por artefato;
- funcionar em Manifest V3.

---

## Limitações

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

Resultado parcial não deve ser tratado como coleta completa.

---

## Segurança, privacidade e uso responsável

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

## Autor

**Guilherme Caselli**  
Delegado de Polícia  
Professor da Academia de Polícia de São Paulo  
Autor de *Manual de Investigação Digital* — Editora Juspodivm

Instagram:  
`https://instagram.com/guilhermecaselli`

Página do autor:  
`https://www.editorajuspodivm.com.br/authors/page/view/id/206/`

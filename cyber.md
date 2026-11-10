---
marp: true
theme: gaia
class: invert
paginate: true
html: true
style: |
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap');

  :root {
    --bg-dark:    #0D0D0F;
    --bg-card:    #131317;
    --bg-mid:     #1A1A22;
    --accent:     #A78BFA;
    --accent-2:   #34D399;
    --accent-3:   #F472B6;
    --text-main:  #F0EEF8;
    --text-muted: #7B7A8E;
    --border:     rgba(167,139,250,0.15);
    --color-background: #0D0D0F;
    --color-background-code: #131317;
    --color-background-paginate: #0D0D0F;
    --color-foreground: #F0EEF8;
    --color-highlight: #A78BFA;
    --color-highlight-hover: #C4B5FD;
  }
 

  /* ── Força fundo escuro em TUDO — anula qualquer herança do tema ── */
  section,
  section *,
  section *::before,
  section *::after {
    box-sizing: border-box !important;
  }

  section {
    font-family: 'DM Sans', sans-serif !important;
    font-size: 30px !important;
    background-color: #0D0D0F !important;
    color: #F0EEF8 !important;
    padding: 44px 60px !important;
    overflow: visible !important;
    position: relative !important;
  }
  
  section::before {
    content: '' !important;
    position: absolute !important;
    inset: 0 !important;
    background:
      radial-gradient(ellipse 70% 50% at 85% 10%, rgba(167,139,250,0.08) 0%, transparent 60%),
      radial-gradient(ellipse 50% 40% at 10% 90%, rgba(52,211,153,0.06) 0%, transparent 55%) !important;
    pointer-events: none !important;
    z-index: 0 !important;
  }

  section::after {
    font-family: 'DM Mono', monospace !important;
    font-size: 10px !important;
    color: #7B7A8E !important;
    bottom: 18px !important;
    right: 60px !important;
    background: transparent !important;
  }

  /* ── Zera backgrounds brancos do tema em todos os elementos ── */
  section div, section span, section p,
  section ul, section ol, section li,
  section h1, section h2, section h3, section h4,
  section table, section thead, section tbody,
  section tr, section td, section th,
  section blockquote, section pre, section code,
  section figure, section figcaption, section header, section footer {
    background-color: transparent !important;
    background: transparent !important;
  }

  /* ── Headings ── */
  section h1, section h2, section h3 {
    font-family: 'Syne', sans-serif !important;
    letter-spacing: -0.03em !important;
    margin: 0 0 0.3em !important;
    color: #F0EEF8 !important;
  }

  section h1 { font-size: 3rem !important;    font-weight: 800 !important; line-height: 1.08 !important; }
  section h2 { font-size: 1.65rem !important; font-weight: 700 !important; }
  section h3 { font-size: 0.95rem !important; font-weight: 600 !important; color: #A78BFA !important; margin-bottom: 0.2em !important; }

  section p {
    font-size: 0.95rem !important;
    font-weight: 300 !important;
    line-height: 1.6 !important;
    color: #C2BFDA !important;
    margin: 0 0 0.55em !important;
  }

  section strong { color: #F0EEF8 !important; font-weight: 600 !important; }
  section em     { color: #34D399 !important; font-style: normal !important; font-weight: 400 !important; }

  section code {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.82em !important;
    background-color: rgba(167,139,250,0.15) !important;
    border: 1px solid rgba(167,139,250,0.25) !important;
    border-radius: 5px !important;
    padding: 1px 5px !important;
    color: #C4B5FD !important;
  }

  section pre {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-radius: 10px !important;
    padding: 14px 18px !important;
    font-family: 'DM Mono', monospace !important;
    font-size: 0.76rem !important;
    line-height: 1.55 !important;
    color: #A0E8C0 !important;
    overflow: hidden !important;
    margin: 0 !important;
  }

  section pre code {
    background: transparent !important;
    border: none !important;
    padding: 0 !important;
    color: #A0E8C0 !important;
    font-size: 1em !important;
  }

  section ul {
    list-style: none !important;
    padding: 0 !important;
    margin: 0 !important;
  }

  section ul li {
    padding: 0.28em 0 0.28em 1.4em !important;
    position: relative !important;
    font-size: 0.9rem !important;
    font-weight: 300 !important;
    color: #C2BFDA !important;
    line-height: 1.45 !important;
  }

  section ul li::before {
    content: '▸' !important;
    position: absolute !important;
    left: 0 !important;
    color: #A78BFA !important;
    font-size: 0.72em !important;
    top: 0.48em !important;
  }

  section hr {
    border: none !important;
    height: 1px !important;
    background: linear-gradient(90deg, #A78BFA 0%, transparent 100%) !important;
    margin: 0.9em 0 !important;
    opacity: 0.35 !important;
  }

  /* ── Tabelas de conteúdo (markdown) ── */
  section table:not(.cols) {
    width: 100% !important;
    border-collapse: collapse !important;
    font-size: 0.84rem !important;
  }

  section table:not(.cols) th {
    font-family: 'Syne', sans-serif !important;
    font-size: 0.72rem !important;
    font-weight: 700 !important;
    text-transform: uppercase !important;
    letter-spacing: 0.08em !important;
    color: #A78BFA !important;
    border-bottom: 1px solid rgba(167,139,250,0.15) !important;
    padding: 8px 12px !important;
    text-align: left !important;
    background: transparent !important;
  }
  
  section table:not(.cols) td {
    padding: 8px 12px !important;
    border-bottom: 1px solid rgba(255,255,255,0.01) !important;
    color: #C2BFDA !important;
    font-weight: 300 !important;
    background: transparent !important;
  }
  
  section table:not(.cols) {
    outline: 1px solid rgba(255,255,255,0.04) !important;
    outline-offset: 0px !important;
  }

  section table:not(.cols) td {
    padding: 8px 12px !important;
    border-bottom: none !important;        /* remove borda por linha */
    color: #C2BFDA !important;
    font-weight: 300 !important;
    background: transparent !important;
  }
  
  section table:not(.cols) th {
    border-bottom: 1px solid rgba(167,139,250,0.4) !important;  /* só o cabeçalho */
    padding: 8px 12px !important;
    /* resto igual */
  }
  
  section table:not(.cols) tbody tr {
    border-bottom: 1px solid rgba(255,255,255,0.04) !important;
  }

  .table-wrap {
    border: 1px solid rgba(255,255,255,1) !important;
    border-radius: 8px !important;
    overflow: overflow !important;
  }


  /* ── Blockquote ── */
  section blockquote {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-left: 3px solid #A78BFA !important;
    border-radius: 10px !important;
    padding: 12px 18px !important;
    margin: 0.7em 0 0.7em !important;
    font-size: 0.9rem !important;
    color: #C2BFDA !important;
    font-style: normal !important;
  }

  section blockquote p      { margin: 0 !important; color: #C2BFDA !important; font-size: 0.9rem !important; }
  section blockquote strong { color: #A78BFA !important; }

  /* ════ SLIDE CLASSES ════ */

  section.hero {
    display: flex !important;
    flex-direction: column !important;
    justify-content: center !important;
    font-size: 26px !important;
    padding: 56px 68px !important;
    background-color: #0D0D0F !important;
  }

  section.hero h1 {
    font-size: 3.8rem !important;
    background: linear-gradient(135deg, #fff 30%, #A78BFA 70%, #34D399 100%) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    background-clip: text !important;
    margin-bottom: 0.15em !important;
  }

  section.hero .subtitle {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.88rem !important;
    color: #A78BFA !important;
    letter-spacing: 0.1em !important;
    text-transform: uppercase !important;
    margin-bottom: 1.2em !important;
    background: transparent !important;
  }

  section.hero p { max-width: 560px !important; font-size: 1rem !important; color: #A09EC0 !important; }

  section.divider {
    display: flex !important;
    flex-direction: column !important;
    justify-content: center !important;
    font-size: 25px !important;
    background-color: #1A1A22 !important;
  }

  section.divider h2 {
    font-family: 'Syne', sans-serif !important;
    font-size: 2.8rem !important;
    font-weight: 800 !important;
    letter-spacing: -0.04em !important;
    background: linear-gradient(120deg, #fff 0%, #A78BFA 100%) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    background-clip: text !important;
    margin: 0 !important;
  }

  section.divider .label {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.9rem !important;
    letter-spacing: 0.14em !important;
    text-transform: uppercase !important;
    color: #7B7A8E !important;
    margin-bottom: 0.5em !important;
    background: transparent !important;
  }

  section.closing {
    display: flex !important;
    flex-direction: column !important;
    justify-content: center !important;
    text-align: center !important;
    align-items: center !important;
    font-size: 25px !important;
    background-color: #0D0D0F !important;
  }

  section.closing h1 {
    font-size: 3.2rem !important;
    background: linear-gradient(135deg, #fff 20%, #A78BFA 60%, #34D399 100%) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    background-clip: text !important;
  }

  section.closing p { max-width: 480px !important; text-align: center !important; }

  section table.cols {
    display: table !important;
    width: 100% !important;
    max-width: 100% !important;
    table-layout: fixed !important; /* extra: garante que os % sejam respeitados */
  }
  
  section img { max-width: 100% !important; }
  
  section ul li { font-size: 0.75rem !important; } /* ou o tamanho que couber */
  
  /* ════ COMPONENTS ════ */

  .card {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-radius: 12px !important;
    padding: 16px 18px !important;
  }

  .card .num {
    font-family: 'Syne', sans-serif !important;
    font-size: 2.2rem !important;
    font-weight: 800 !important;
    color: #A78BFA !important;
    line-height: 1 !important;
    margin-bottom: 4px !important;
    background: transparent !important;
  }

  .card .label {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.7rem !important;
    letter-spacing: 0.1em !important;
    text-transform: uppercase !important;
    color: #7B7A8E !important;
    background: transparent !important;
  }

  .card p { font-size: 0.82rem !important; margin: 6px 0 0 !important; color: #7B7A8E !important; line-height: 1.4 !important; }

  .tag {
    display: inline-block !important;
    font-family: 'DM Mono', monospace !important;
    font-size: 0.68rem !important;
    letter-spacing: 0.07em !important;
    text-transform: uppercase !important;
    padding: 3px 9px !important;
    border-radius: 100px !important;
    background-color: rgba(167,139,250,0.12) !important;
    border: 1px solid rgba(167,139,250,0.25) !important;
    color: #A78BFA !important;
    margin-right: 5px !important;
    margin-bottom: 5px !important;
  }

  .tag.green { background-color: rgba(52,211,153,0.1) !important;  border-color: rgba(52,211,153,0.25) !important;  color: #34D399 !important; }
  .tag.pink  { background-color: rgba(244,114,182,0.1) !important; border-color: rgba(244,114,182,0.25) !important; color: #F472B6 !important; }

  .feat {
    display: flex !important;
    align-items: flex-start !important;
    gap: 13px !important;
    padding: 12px 0 12px 0!important;
    border-bottom: 1px solid rgba(255,255,255,0.05) !important;
    background: transparent !important;
  }

  .feat:last-child { border-bottom: none !important; }

  .feat-icon {
    width: 34px !important;
    height: 34px !important;
    min-width: 34px !important;
    border-radius: 9px !important;
    background-color: rgba(167,139,250,0.12) !important;
    border: 1px solid rgba(167,139,250,0.2) !important;
    display: flex !important;
    align-items: center !important;
    justify-content: center !important;
    font-size: 1rem !important;
    margin-top: 1px !important;
  }

  .feat-body h3 { font-size: 0.88rem !important; color: #F0EEF8 !important; margin: 0 0 3px !important; background: transparent !important; }
  .feat-body p  { font-size: 0.8rem !important;  color: #7B7A8E !important; margin: 0 !important; line-height: 1.45 !important; }

  /* ── Tabela de layout de colunas (não-conteúdo) ── */
  table.cols, table.cols tr,
  table.cols td, table.cols th {
    border: none !important;
    background: transparent !important;
    padding: 0 12px 0px 12px !important;
    vertical-align: top !important;
    border-bottom: none !important;
  }

  
  .compare-col {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-radius: 12px !important;
    padding: 16px 18px !important;
  }

  .compare-col.hl {
    border-color: rgba(167,139,250,0.4) !important;
    background-color: rgba(167,139,250,0.06) !important;
  }

  .compare-col h3 {
    font-size: 0.92rem !important;
    margin-bottom: 10px !important;
    padding-bottom: 10px !important;
    border-bottom: 1px solid rgba(167,139,250,0.15) !important;
    color: #F0EEF8 !important;
    background: transparent !important;
  }
  /* ── Tabelas de conteúdo (markdown) ── */
    section table:not(.cols) {
      width: 100% !important;
      border-collapse: collapse !important;
      font-size: 0.84rem !important;
    }
  
    /* Estilo do cabeçalho SEM bordas */
    section table:not(.cols) th {
      font-family: 'Syne', sans-serif !important;
      font-size: 0.72rem !important;
      font-weight: 700 !important;
      text-transform: uppercase !important;
      letter-spacing: 0.08em !important;
      color: #A78BFA !important;
      background: transparent !important;
      text-align: left !important;
      padding: 12px 12px !important;
      border: none !important; /* Remove a borda inferior do cabeçalho */
    }
    
    /* Estilo das células SEM bordas */
    section table:not(.cols) td {
      padding: 8px 12px !important;
      color: #C2BFDA !important;
      font-weight: 300 !important;
      background: transparent !important;
      border: none !important; /* Remove as bordas entre as linhas */
    }
  
    /* Garantia extra para remover qualquer borda aplicada diretamente na linha */
    section table:not(.cols) tr {
      border: none !important;
    }
  
    /* Mantém APENAS a borda externa do wrapper */
    .table-wrap {
      /* Usei 0.15 de opacidade para a borda branca ficar sutilmente visível. 
         Se quiser mais apagado, volte para 0.04 */
      border: 1px solid rgba(255, 255, 255, 0.15) !important; 
      border-radius: 8px !important;
      overflow: hidden !important; /* Impede que o fundo da tabela vaze pelas bordas arredondadas */
    }

    section p.caption {
      font-size: 14px !important;
      line-height: 1.3 !important;
      color: #7B7A8E !important;
      margin: 8px 0 0 !important;
    }
  
---

<!-- _class: hero -->

# Cyber
<h2> Educação contra a desinformação</h2>

<p></p>

<div style="margin-top:1.4em">
  <span class="tag">Cidadania Digital</span>
  <span class="tag green"><i>Fake-News</i></span>
  <span class="tag pink">Redes Sociais</span>
</div>

<br>

<br>

<div class="subtitle">Apresentação + Jogo Digital Interativo</div>

---

<!-- _class: divider -->

<div class="label">01 — Contextualização</div>

## Quem somos?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"></p>

---

## Curso

- Discentes do curso de Tecnologia em Analise e Desenvolvimento de Sistemas do IFCE Campus Itapipoca.

<br>

## Projeto

- Bytes para Cidadania: Projeto que engloba 4 ações de extensão visando a **promoção da Cidadania Digital nas escolas**.

<br>

## Nossa ação

- Ação de extensão Cyber: Trabalha o assunto de **<i>Fake-news</i> e desinformação** nas escolas. 

---

<!-- _class: divider -->

<div class="label">01 — Contextualização</div>

## O que é Cidadania Digital?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"></p>

---

## O que é?

- Cidadania Digital pode ser entendido como a capacidade de um indivíduo de participar da sociedade por meio de recursos online, abrangendo tanto o acesso aos dispositivos e meios necessários quanto às habilidades sociocomportamentais requeridas (SILVEIRA, 2010).

<br>

### Para além do domínio dos recursos tecnológicos:

- A Cidadania Digital não depende apenas do acesso e do domínio tecnológico, mas também da compreensão dos mecanismos, algoritmos e formas de interação existentes no ciberespaço.

---

## Inteligência digital

<p style="font-size: 25px !important"> O Digital Inteliggence Framework (DK Framework) do Institute of Electrical and Electronics Engineers (IEEE), elenca 8 competências para Cidadania Digital: </p>

- Identidade do cidadão;
- Equilíbrio no uso da tecnologia;
- Gestão de riscos cibernéticos comportamentais;
- Gestão de segurança cibernética pessoal;
- Empatia digital;
- Gestão de pegada digital;
- Gestão de privacidade;
- **Letramento midiático e informacional: possuir meios de encontrar, organizar, avaliar e analisar as informações e conteúdos de mídias consumidos, exercendo postura crítica diante deles**.

---

## Conclusão

Cidadania Digital pode ser entendida como a capacidade de usar a tecnologia e as mídias digitais de forma **segura**, **responsável** e **ética**.

---

<!-- _class: divider -->

<div class="label">02 — Conteúdo</div>

## <i>Fake-News</i>

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"></p>


---

<img style="margin: auto;" src="./assets/cha-anuncio.jpeg" height="100%">
<img src="./assets/cara-assustada.jpeg" height="100%">

---

## O fenômeno das <i>Fake News</i>


<table class="cols">
<tr>
<td width="40%">

- Informações falsas apresentadas como verdadeiras.
- Conteúdos que imitam notícias e fontes confiáveis.
- Disseminação acelerada pelas redes sociais.
- Compartilhamentos sem verificação dos fatos.

<br>

</td>
<td width="60%">

<img src="./assets/fake-news-celular.jpeg" style="width:100%;object-fit:cover;border-radius:12px;">

</td>
</tr>
</table>


---

## Desordem informacional


<table class="cols">
<tr>
<td width="50%">

- Excesso de informações circulando no ambiente digital.
- Conteúdos falsos, manipulados ou descontextualizados.
- Diferentes níveis de intenção e propósito.
- Classificação proposta por Wardle e Derakhshan (2017).

<br>

</td>
<td width="50%">

<img src="./assets/desinformation.jpeg" style="width:100%;object-fit:cover;border-radius:12px;">

</td>
</tr>
</table>


---

## IA Generativa e Fake News

<table class="cols">
<tr>
<td width="45%">

- Uso de IA para manipular rostos e vozes (Deepfake).
- Simulação de recomendações de pessoas famosas.
- Produtos milagrosos e promessas de cura.
- Uso indevido da imagem de profissionais para gerar confiança.
- Golpes financeiros e riscos à saúde.

<br>

</td>
<td width="55%">

<img src="./assets/drauzio.jpeg" style="width:100%;object-fit:cover;height:400px;border-radius:12px;">
    
<p class="caption">
  Captura utilizada pelo Estadão Verifica em uma checagem de outro vídeo falso envolvendo Drauzio Varella. A imagem mostra a alegação falsa de cura do diabetes.
</p>

</td>
</tr>
</table>

---

## Combate às Fake News e cidadania digital

<table class="cols">
<tr>
<td width="50%">

- Verificar a fonte e a autoria da informação.
- Comparar a notícia com outros veículos confiáveis.
- Conferir datas, imagens e contexto.
- Desconfiar de promessas exageradas e conteúdos sensacionalistas.
- Evitar compartilhar informações sem confirmação.
- Desenvolver pensamento crítico e responsabilidade digital.

<br>

</td>
<td width="50%">

<img src="./assets/fake-lupa.jpeg" style="width:100%;object-fit:cover;height:520px;border-radius:12px;">

</td>
</tr>
</table>

---

## Pergunta:

Se uma informação parece verdadeira, tem milhares de curtidas e foi compartilhada por pessoas em quem confiamos, isso significa que podemos acreditar nela?

---

<!-- _class: divider -->

<div class="label">02 — Conteúdo</div>

## Identificar informações falsas

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"></p>

---

## Como identificar e investigar?

<table class="cols">
<tr>
<td width="50%">

### Hierarquia de fontes
  - Priorizar fontes originais e oficiais.
  - Conferir a origem da informação.
  - Exemplos: editais, comunicados e portais oficiais.


<br>

</td>
<td width="50%">

### Leitura lateral
- Sair da publicação suspeita.
- Pesquisar em outras fontes.
- Comparar informações antes de acreditar.
- Sinais de alerta (Red Flags)
- Links suspeitos.
- Ausência de datas ou comprovações.
- Apelos como "compartilhe agora!".

</td>
</tr>
</table>

---

## Combate e prevenção

<table class="cols">
<tr>
<td width="50%">

### Debunking — Corrigir
- Desmentir informações falsas com evidências.
- Apresentar o fato correto.
- Explicar o erro e indicar fontes confiáveis.


<br>

</td>
<td width="50%">

### Prebunking — Prevenir
- Reconhecer estratégias de manipulação.
- Desenvolver pensamento crítico.
- Criar o hábito de verificar informações.

</td>
</tr>
</table>


<!-- _class: divider

<div class="label">02 — Conteúdo</div>

## Porquê
## acreditamos em fake-news?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"></p>

---

<table class="cols">
<tr>
<td width="50%">

## Psicologia Cognitiva e Social da Desinformação

- Emoções e tomada de decisões.
- Influência social no compartilhamento de informações.

<br>

</td>
<td width="50%">

## Sistema 1 e Sistema 2

- Daniel Kahneman — Dois sistemas de pensamento
- Sistema 1: rápido, automático e impulsivo.
- Sistema 2: lento, analítico e racional.
- Fake news exploram reações imediatas.
- Compartilhamento sem verificação.
- Exemplo: mensagem falsa sobre o bloqueio do WhatsApp.

</td>
</tr>
</table>

---

<table class="cols">
<tr>
<td width="50%">

## Sequestro Emocional

- Uso de emoções para influenciar decisões.
- Medo, ansiedade e urgência.
- Redução da capacidade de análise.
- Reações impulsivas diante de situações de pressão.
- Exemplo: falso pedido de dinheiro após suposto acidente.

</td>
<td width="50%">

## Psicologia Social do Boato

- Três processos de transformação dos boatos:
- Nivelamento: perda de detalhes.
- Acentuação: exagero de informações.
- Assimilação: adaptação às crenças pessoais.

</td>
</tr>
</table>

--- -->

<!-- _class: divider

<div class="label">02 — Conteúdo</div>

## Saúde digital

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"></p>

---

<table class="cols">
<tr>
<td width="50%">

## Equilíbrio no uso da tecnologia

- Gerenciar o tempo de tela e o consumo de informações.
- Utilizar a tecnologia de maneira consciente e saudável.

<br>

</td>
<td width="50%">

## Doomscrolling

- Consumo compulsivo de notícias e conteúdos motivado pela ansiedade.
- Pode aumentar o estresse, prejudicar o sono e comprometer a atenção e a memória.

</td>
</tr>
</table>

## Autocuidado e colaboração

- Reconhecer os próprios limites no ambiente digital.
- Equilibrar participação online, descanso e responsabilidades compartilhadas.


--- -->

<!-- _class: divider

<div class="label">02 — Conteúdo</div>

## Golpes Virtuais

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"></p>

---

<table class="cols">
<tr>
<td width="50%">

## O que são golpes virtuais?
- Fraudes no ambiente digital;
- Manipulação e engano;
- Roubo de dados e dinheiro.

<br>

</td>
<td width="50%">

## Relação entre Fake News e golpes virtuais
- Disseminação de informações falsas;
- Notícias e anúncios fraudulentos;
- Falsas promoções e oportunidades;
- Links maliciosos disfarçados de notícias.


</td>
</tr>
</table>

---

<table class="cols">
<tr>
<td width="50%">

## Principais tipos de golpes
- Phishing;
- Falsas ofertas e promoções;
- Golpes envolvendo Pix;
- Perfis e páginas falsas;
- Falsos comunicados institucionais.

<br>

</td>
<td width="50%">


## Estratégias utilizadas pelos criminosos
- Engenharia social;
- Manipulação emocional;
- Sensacionalismo e urgência;
- Uso da confiança e da desinformação.

</td>
</tr>
</table>


---

<img src="./assets/golpe-falsa-encomenda.jpeg" style="width:100%;object-fit:cover;height:700px;border-radius:12px;">
-->

---

<!-- _class: closing -->

# Cyber
## No combate à desinformação

<div style="margin-top:1.6em;display:flex;gap:10px;justify-content:center;flex-wrap:wrap">
  <span class="tag">IFCE Campus Itapipoca</span>
  <span class="tag green">Bytes para Cidadania</span>
</div>

---

## Fontes

<br>

- <a href="./">Documento: "PROJETO DE CURRICULARIZAÇÃO DA EXTENSÃO
“Bytes para Cidadania”"</a>
- <a href="https://www.educamaisbrasil.com.br/educacao/dicas/o-que-sao-fake-news"> O QUE são fake news? Educa Mais Brasil, [S. l.], 2019. Dicas de Educação. Disponível em: https://www.educamaisbrasil.com.br/educacao/dicas/o-que-sao-fake-news. Acesso em: 16 set. 2026.</a>
- <a href="https://doi.org/10.1590/SciELOPreprints.3294"> FORSTER, Renê et al. Fake News: O que é, como se faz e por que funciona? SciELO Preprints, 7 dez. 2021. DOI: https://doi.org/10.1590/SciELOPreprints.3294. Acesso em: 19 set. 2026. </a>
- <a href="https://rm.coe.int/information-disorder-toward-an-interdisciplinary-framework-for-researc/1680762703"> WARDLE, Claire; DERAKHSHAN, Hossein. Information Disorder: Toward an interdisciplinary framework for research and policymaking. Strasbourg: Council of Europe, 2017. Disponível em: https://rm.coe.int/information-disorder-toward-an-interdisciplinary-framework-for-researc/1680762703. Acesso em: 20 set. 2026. </a>


--- 

## Fontes

<br>

- <a href="https://www.estadao.com.br/estadao-verifica/drauzio-varella-remedio-diabetes-ia/"> MARSCHALL, Luciana. É falso que Drauzio Varella tenha indicado remédio que promete curar diabetes. Disponível em: <https://www.estadao.com.br/estadao-verifica/drauzio-varella-remedio-diabetes-ia/>. Acesso em: 3 nov.. 2026. </a>
- <a href="https://cartilha.cert.br/">CERT.br. Cartilha de Segurança para Internet.</a>
- <a href="#">BRASIL. Ministério da Justiça e Segurança Pública. Prevenção contra golpes na internet.</a>
- <a href="#">POLÍCIA FEDERAL. Cartilhas de Segurança da Informação.</a>
- <a href="#">GABINETE DE SEGURANÇA INSTITUCIONAL. Materiais Educativos em Cibersegurança.</a>

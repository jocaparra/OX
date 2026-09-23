# EVA: VC Due Diligence Autopilot

Landing page da **EVA**, um analista de IA que faz a due diligence de deals para fundos de Venture Capital, do começo ao fim.

## Sobre o produto

A EVA recebe os documentos de um deal (pitch deck, cap table, demonstrativos) e entrega o memorando de investimento pronto para o comitê:

- **Verificação na web (computer use):** navega pelo site oficial, pelo LinkedIn e por notícias públicas da startup para conferir se time, produto e tração declarados batem com a realidade. Aponta divergências e para com transparência se encontrar um CAPTCHA.
- **Memorando de investimento:** DCF, auditoria de cap table e tese de investimento, citando a fonte exata de cada número e afirmação.
- **Dossiê fiscal:** lê SPED, ECD e ECF para encontrar passivos fiscais ocultos.
- **Execução 100% local:** os documentos do deal não saem da máquina do fundo, e um log auditável registra cada chamada externa.

O público são GPs, partners, analistas e associates de fundos de VC no Brasil que investem em Pre-Seed, Seed e Série A.

## Estrutura do repositório

| Caminho | Conteúdo |
| --- | --- |
| `index.html` | A landing page inteira: HTML, CSS e JavaScript no mesmo arquivo |
| `assets/` | Imagens, logos, favicon e o vídeo do hero (`Video hero.mp4`) usados pela página |
| `vercel.json` | Configuração de deploy na Vercel |

### Seções da página

Nav, Hero (com vídeo), Problema, Plataforma, Como funciona, Para quem, FAQ e Rodapé.

### Idiomas

A página abre em inglês e tem um seletor de idioma para português. Os textos traduzidos ficam num dicionário no script do final de `index.html`, e cada elemento traduzível tem um atributo `data-i18n` com a chave correspondente. Para mudar um texto, altere a chave nos dois idiomas.

Os botões de contato levam para o WhatsApp (`w.app/evaen`, `w.app/evabr`, `w.app/evaesp`).

## Rodar localmente

O site é estático, sem build nem dependências. Abra o `index.html` no navegador ou suba um servidor local:

```bash
python3 -m http.server 8000
```

Depois acesse http://localhost:8000.

## Deploy

O deploy é feito pela **Vercel**: cada push no `main` publica o site automaticamente. O `vercel.json` ativa URLs sem extensão (`cleanUrls`) e redireciona `/evanewlp` e `/indexv2` para `/`.

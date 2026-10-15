# Análise da Landing Page NovaWeb Studio

15/10/2026 · Gustavo Fraga

Sou estudante do 1º período (1ª fase) do curso de Análise e Desenvolvimento de Sistemas da FMP e criei a landing page **NovaWeb Studio** como projeto prático de front-end, aplicando HTML. Este relatório examina o código-fonte do repositório [g-fraga/NovaWeb](https://github.com/g-fraga/NovaWeb).

## 1. Apresentação e Contexto

**Autor:** Gustavo Fraga, estudante de Análise e Desenvolvimento de Sistemas, 1ª fase, FMP. O projeto reflete o início da formação: foco em estrutura semântica, estilização moderna e boas práticas básicas.

**Visão geral:** a NovaWeb é uma página única (one-page) que apresenta um estúdio de desenvolvimento web. Ela tem quatro blocos: cabeçalho com botão de WhatsApp, seção principal (hero) com mockup de navegador, grade com três serviços e um rodapé com chamada final. O repositório é enxuto: um `index.html` de cerca de 14,6 KB, quatro imagens e um README com apenas o título. O propósito prático da página é um só: levar o visitante a iniciar uma conversa pelo WhatsApp.

## 2. Objetivo da Empresa / Projeto

**Propósito:** vender serviços de criação de sites, landing pages, e-commerces e web apps, conforme a descrição da página.

**Proposta de valor:** sites rápidos, com design limpo, "nota máxima de performance" e entrega "em dias, não em semanas".

**Público-alvo:** pequenos e médios negócios, empreendedores e profissionais autônomos brasileiros. O fechamento por WhatsApp, o botão "Orçamento Rápido" e a promessa de transformar visitas em vendas.

**Como a mensagem se desenvolve:**

1. **Promessa:** o título H1 fala de resultado ("transformam visitas em vendas").
2. **Como:** o subtítulo cita design, performance e prazo.
3. **Oferta:** três cartões de serviços.
4. **Urgência:** "Respondemos em até 20 minutos" no rodapé.

O fio condutor é claro. Um ponto de atenção: os cartões incluem SaaS e Growth Marketing, o que amplia o escopo além da promessa inicial de "sites rápidos".

## 3. Identidade Visual e Paleta de Cores

A paleta é definida em um único `tailwind.config` e segue uma lógica de três famílias, com o azul como cor de ação.

| Papel | Cor (token) | HEX | Onde aparece |
| --- | --- | --- | --- |
| Fundo | canvas | `#F8FAFC` | Fundo da página |
| Principal | brand-500 / brand-600 | `#3B82F6` / `#2563EB` | Botão "Orçamento Rápido", selo e links |
| Secundária | sage-500 / sage-100 | `#10B981` / `#D1FAE5` | Gradiente do título, cadeado, mancha de fundo |
| Texto e contraste | slate-900 / 600 / 500 | `#0F172A` / `#475569` / `#64748B` | Títulos, corpo, descrições |
| Ação alternativa | slate-900 | `#0F172A` | Botão "Falar no WhatsApp" |
| Destaque | amber-400 | `#FBBF24` | Estrelas de avaliação |

**Psicologia e harmonia:** o azul transmite confiança e tecnologia, o verde sálvia sugere crescimento e resultado, e o gradiente entre os dois reforça a ideia de evolução. Como são cores frias e de baixa agressividade, o conjunto fica harmônico e profissional, adequado a um estúdio de tecnologia. O fundo quase branco e as sombras suaves dão a sensação de limpeza.

**Contraste e hierarquia** (razões de contraste calculadas por mim, aproximadas):

- Títulos em #0F172A sobre o fundo claro chegam a cerca de 17:1, e o texto de corpo a cerca de 7:1. Ambos são excelentes.
- Texto branco sobre o botão #3B82F6 fica perto de 3,7:1, abaixo dos 4,5:1 da WCAG AA para texto pequeno. Usar #2563EB (cerca de 5,2:1) resolve.
- O trecho final do gradiente verde no título (#10B981) fica perto de 2,4:1, e o texto do copyright (slate-400) perto de 2,5:1.
- A escala tipográfica é clara: H1 de 36–48 px em extrabold, subtítulo em cinza médio, e o botão azul saturado como único ponto de forte atração visual.

## 4. Análise da Arquitetura e Código

**Estrutura:** o repositório tem 6 arquivos na raiz (`index.html`, `README.md` e 4 imagens). Para este tamanho, a organização simples funciona, mas separar uma pasta `img/` facilitaria o crescimento.

**Pontos fortes do código:**

- Comentários com "✏️" indicam exatamente o que editar (textos, links, cores, logo), o que torna o projeto fácil de reaproveitar.
- As cores ficam centralizadas como tokens no `tailwind.config`, então trocar a paleta é rápido.
- HTML semântico (`header`, `main`, `section`, `article`, `footer`) e hierarquia de títulos coerente: H1, H2 oculto visualmente com `sr-only` e H3 nos cartões.
- Acessibilidade básica: `lang="pt-BR"`, `aria-label` em ícones e navegação, anel de foco com `focus-visible` e `prefers-reduced-motion` para desligar animações.
- Responsividade mobile-first com `sm:` e `lg:`, `loading="lazy"` nos cartões, `preconnect` nas fontes e `rel="noopener"` nos links externos.

## 5. Mapeamento de UX/UI e Componentes

- **Cabeçalho:** logo com ícone em gradiente à esquerda e botão escuro de WhatsApp à direita. Em telas pequenas o texto some e fica só o ícone, uma boa adaptação.
- **Hero:** é a seção mais forte. O selo "Sites & Web Apps sob medida", o título com trecho em gradiente, o subtítulo curto e o botão azul formam uma leitura rápida. O mockup de navegador à direita ilustra o serviço em vez de apenas descrevê-lo.
- **Prova social:** três avatares, cinco estrelas, nota 5/5 e "+120 projetos entregues" dão credibilidade rápida, mas não há depoimentos com nome e empresa.
- **Serviços (benefícios):** três cartões horizontais com miniatura, título e frase curta, com efeito de elevação ao passar o mouse. São escaneáveis, mas as descrições falam de recursos e pouco de resultados para o cliente.
- **FAQ e depoimentos:** não existem nesta versão. É a lacuna mais evidente para quem ainda hesita antes de pedir orçamento.
- **Rodapé:** frase final ("Vamos tirar seu projeto do papel?"), ícones de e-mail, Instagram e GitHub, e copyright com ano automático.

**CTAs e fluxo:** há dois pontos de conversão (cabeçalho e hero), ambos abrindo o WhatsApp com mensagem pré-preenchida, o que reduz o atrito. O fluxo é curto e linear (ler, confiar, chamar), sem menu de navegação, o que combina com uma página única. Após os cartões de serviço e no rodapé, porém, não há um botão de ação repetido.

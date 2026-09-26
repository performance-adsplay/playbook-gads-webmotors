# Design System — Caliber 3135

Documentação técnica e visual do padrão de design extraído da apresentação executiva de diagnóstico (*Webmotors / Caliber 3135*).

---

## 1. Identidade & Filosofia Visual

O design system da **Caliber 3135** combina a sobriedade analítica das principais consultorias de gestão e auditoria técnica (*clean, data-dense, white canvas*) com toques visuais cinematográficos inspirados no setor automotivo e de tecnologia de ponta.

- **Vibe:** Analítica, cirúrgica, executiva, moderna e assertiva.
- **Ritmo de Slides:** 
  - **90% Superfícies Claras (White / Off-White):** Focadas em legibilidade, tabelas, evidências e diagramas de tomada de decisão.
  - **10% Superfícies Escuras (Deep Black & Purple Cinema):** Utilizadas estrategicamente em Capa e Transições de Seção para imprimir autoridade, profundidade e impacto estético.

---

## 2. Paleta de Cores (Color Tokens)

### 2.1 Superfícies (Grounds)
| Token | HEX | Aplicação |
|---|---|---|
| `ground-light` | `#FFFFFF` | Fundo principal da maioria dos slides de diagnóstico e evidências. |
| `ground-subtle` | `#F8F9FA` | Fundo de cartões, linhas alternadas de tabelas e contêineres de código/tagueamento. |
| `ground-dark` | `#000000` | Fundo das transições, divisores de seção e fechamento. |
| `ground-dark-cinema`| `#07040E` / `#0A0318` | Fundo atmosférico com gradientes e arte automotiva da capa. |

### 2.2 Tipografia & Textos
| Token | HEX | Aplicação |
|---|---|---|
| `text-primary` | `#000000` / `#111111` | Títulos principais, métricas em destaque e peso visual dominante. |
| `text-secondary` | `#374151` | Parágrafos explicativos, diagnósticos e descrições de tabelas. |
| `text-muted` | `#6B7280` | Eyebrows/kickers, metadados e termos secundários. |
| `text-footnote` | `#9CA3AF` | Rodapés de fonte, notas legais de confidencialidade e carimbos. |
| `text-on-dark` | `#FFFFFF` | Títulos e textos sobre fundos pretos ou transições escuras. |

### 2.3 Cores de Acento & Destaque (Brand & Mood)
| Token | HEX | Aplicação |
|---|---|---|
| `accent-cobalt` | `#2563EB` / `#1D4ED8` | Azul elétrico do monograma "C" linear da marca. |
| `accent-violet` | `#6B21A8` / `#7C3AED` | Roxo/neon utilizado em iluminações de fundo, brilhos 3D e fibra óptica. |
| `accent-cyan-light` | `#38BDF8` | Reflexos sutis em elementos de tecnologia e feixes de dados. |

### 2.4 Cores Semânticas de Diagnóstico
| Token | HEX | Aplicação |
|---|---|---|
| `status-critical` | `#DC2626` | Nível "Crítica", divergências graves (ex.: discrepância 150×). |
| `status-warning` | `#F59E0B` | Nível "Alta", avisos de duplicidade de pixel, alerta de desvio. |
| `status-info` | `#3B82F6` | Nível "Média", apontamentos estruturais e reorganizações de contas. |
| `status-success` | `#10B981` | Ponto verde de status ativo (*Meta Pixel Helper* / tags funcionais). |

---

## 3. Tipografia

A tipografia é estritamente neo-grotesca, técnica, sólida e de alta densidade informativa.

### 3.1 Família Tipográfica Recomendada
- **Primária:** `Neue Haas Grotesk`, `Helvetica Neue`, `Inter` ou `Arial`.
- **Monospaçada (Tags, Scripts e IDs):** `JetBrains Mono`, `Roboto Mono` ou `Consolas`.

### 3.2 Assinatura da Marca (Logotipo Caliber 3135)
O logotipo adota um contraste proposital de pesos tipográficos no mesmo corpo de texto:
- **`CALIBER`**: Peso **Black (900)** ou **Bold Extended (800)**, caixa alta, tracking compacto (`-0.02em`).
- **`3135`**: Peso **Light (300)** ou **Thin (100)**, caixa alta / alinhamento óptico, tracking neutro a levemente expandido.

### 3.3 Escala Tipográfica (Base 1280×720 / 1920×1080)
| Nível | Peso | Tamanho | Estilo / Caixa |
|---|---|---|---|
| **Top Bar / Confidencial** | Regular (400) | 12px – 13px | Sentence Case, cor cinza média (`#6B7280`). |
| **Kicker / Eyebrow** | Bold (700) | 13px – 14px | UPPERCASE, `letter-spacing: 0.05em`. Ex.: `ANTES DE TUDO · ESCOPO`. |
| **Slide Title (H1)** | Bold (700) | 28px – 34px | Sentence Case, cor preta pura (`#000000`), linha única ou curta. |
| **Lead / Subtítulo** | Regular (400) | 18px – 20px | Sentence Case, contraste balanceado (`#374151`). |
| **Big Numbers (KPI)** | Black (900) | 56px – 72px | Números de impacto com sufixo compacto (ex.: `11`, `52`, `150×`). |
| **Títulos de Cartão (H3)** | Bold (700) | 16px – 18px | UPPERCASE para seções e Sentence Case para itens. |
| **Corpo / Tabelas** | Regular (400) | 14px – 16px | Sentence Case, frases diretas em padrão fragmento/métrica. |
| **Fonte / Footnote** | Regular (400) | 12px – 13px | Sentence Case, posicionado rente ao canto inferior esquerdo. |

---

## 4. Estrutura de Layout & Grid

### 4.1 Header Fixo dos Slides de Conteúdo
Todos os slides com fundo claro seguem uma barra superior utilitária padronizada:
```
+--------------------------------------------------------------------------------+
| Documento Confidencial. Proibido o uso desse documento sem...     CALIBER 3135 |
|                                                                                |
| EYEBROW · SEÇÃO                                                                |
| Título Principal de Impacto                                                    |
| Subtítulo ou linha de contexto do diagnóstico                                  |
+--------------------------------------------------------------------------------+
```

### 4.2 Margens e Espaçamentos
- **Padding Geral:** `40px 56px` (no canvas 1280×720) ou `60px 80px` (no canvas 1920×1080).
- **Gap entre Blocos/Colunas:** `20px` a `28px`.
- **Alinhamento:** Rigorosamente alinhado à esquerda para leitura escaneável, com rodapé de fontes fixo no limite inferior.

---

## 5. Biblioteca de Componentes

### 5.1 Tabela de Sumário Executivo / Frentes
- **Cabeçalho:** Fundo branco ou cinza ultra-leve com texto em caixa alta, negrito e sem serifa.
- **Linhas:** Divisores sutis em cinza claro (`border-bottom: 1px solid #E5E7EB`).
- **Níveis de Criticidade:**
  - `Crítica` destacado em vermelho escuro.
  - `Alta` destacado em laranja/âmbar escuro.
  - `Média` em azul/cinza escuro.
- **Direcionamento de Ação:** Uso consistente de seta indicativa `→` para ações de curto prazo com prazos entre parênteses: `(1 semana)`.

### 5.2 Big Numbers / Prova Quantitativa
- Grid de 3 a 4 colunas horizontais.
- O número gigante fica posicionado no topo (`56px - 72px`), seguido imediatamente por um fragmento descritivo sucinto e objetivo (ex.: `52 datasets no inventário`).
- Sem cards ou molduras decorativas; o espaço em branco ao redor do número cria o peso visual.

### 5.3 Cartões de Evidência / Auditoria
- Superfície clara com borda neutra sutil (`1px solid #E5E7EB`) e cantos levemente arredondados (`border-radius: 8px`).
- Inclusão de capturas reais de telas de auditoria (ex.: *Meta Pixel Helper*, configurações de conversão do Google Ads) para sustentação empírica dos achados.
- Chamada contrastada inferior (ex.: `Valor-padrão: R$ 150` vs `Valor-padrão: R$ 1`).

### 5.4 Grid Numérico de Plano Imediato (Quick Wins)
- Matriz de 3 colunas × 2 linhas.
- Numeração de dois dígitos em destaque (`01`, `02`, `03`...) no topo de cada bloco em peso pesado.
- Título do quick win em caixa alta, conciso e imperativo (`ENSINAR AO ALGORITMO O QUE IMPORTAR`).
- Texto de suporte com até 15 palavras.

### 5.5 Banner de Atenção / Callout
- Bloco inferior ou destacado em caixa com tom neutro ou advertência suave:
  - Título em destaque: **Atenção**
  - Texto explicativo antecipando efeitos colaterais das mudanças técnicas (ex.: queda temporária no volume reportado ao limpar duplicações).

---

## 6. Iconografia & Grafismos

- **Logotipo Ícone:** Círculo estilizado formado por linhas horizontais azuis paralelas com corte central representando a letra "C".
- **Separadores e Conectores:** 
  - Marcador de meio-ponto: `·` (usado entre seções, ex.: `ANTES DE TUDO · ESCOPO`).
  - Setas de direcionamento: `→` (apontando ações imediatas).
  - Marcador de comparação: `×` (ex.: `Adjust × Firebase`).
- **Fotografia / 3D Art:**
  - Estilo automotivo noturno (*midnight/high-speed*).
  - Render 3D de alta fidelidade com reflexos roxos e azuis, trilhas de luz contínuas sobre asfalto molhado/espelhado.

---

## 7. Tom de Voz & Gramática de Redação

1. **Afirmações Diretas e Indiscutíveis:** Títulos declarativos que resumem a constatação, nunca perguntas genéricas.
   - *Exemplo:* "A arquitetura atual de mensuração apresenta fragmentação, gera dados inconsistentes e limita a eficiência da otimização de mídia".
2. **Causa Raiz sobre Sintoma:** Posicionamento de liderança de consultoria que analisa além do código.
   - *Exemplo:* "Não é uma falha técnica. É um sintoma de organização".
3. **Citação e Auditoria Forense:** Sempre especificar fontes, datas, IDs e rotas auditadas para conferir validade irrefutável aos dados.
```
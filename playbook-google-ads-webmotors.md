---
titulo: Playbook de Operação — Google Ads Webmotors
versao: v1.0
data: 26/09/2026
escopo: WM | Comprar · WM | Expansão · WM | Vender · Webmotors | Santander Financiamentos
base: auditorias de conta com corte em 31/08/2026, atualizadas até 25/09/2026
publico: time de operação de mídia Webmotors
---

# Playbook de Operação — Google Ads Webmotors

Material de handover e consulta para a operação das quatro contas primárias de Google Ads da Webmotors. Cada item parte de uma **situação observável na conta** e leva até a ação recomendada, com o limite de autonomia de quem executa e a fonte que sustenta a decisão.

---

## 1. Como usar este playbook

### 1.1 O framework

Cada item do playbook segue a mesma estrutura:

| Campo | O que responde |
|---|---|
| **Situação** | O que o operador vê na conta (o gatilho). |
| **Diagnóstico** | Por que isso acontece, qual é a causa provável. |
| **Como verificar** | Onde clicar, qual relatório ou segmentação abrir para confirmar. |
| **Recomendação** | O que fazer. |
| **Guardrail** | O que não fazer junto, o cuidado para não quebrar o aprendizado ou a leitura. |
| **Escopo** | Em quais das quatro contas o item se aplica hoje. |
| **Status** | Nível de validação do item (ver legenda). |
| **Prioridade** | Alta, Média ou Baixa. |
| **Autonomia** | Quem pode executar sem aprovação (ver legenda). |
| **Dono** | Time responsável pela execução. |
| **Referência Google** | Artigo oficial do Google Ads Help, quando existir. |
| **Evidência interna** | Auditoria ou estudo que originou o item. |

**Regra de precedência:** quando a boa prática genérica do Google e a evidência interna da conta divergirem, **a evidência interna prevalece**. Exemplos: Search Partners não deve ser desligado em WM | Comprar, e a ausência de campanha de marca dedicada é uma decisão deliberada.

### 1.2 Legendas

**Status**

| Status | Significado |
|---|---|
| ✅ Executado | Ajuste já aplicado na conta. Manter e monitorar. |
| 🟢 Confirmado | Diagnóstico comprovado por dado. Pode virar procedimento. |
| 🟡 Em avaliação | Diagnóstico comprovado, mas a ação depende de decisão de negócio. |
| 🔵 Hipótese | Ainda não comprovado. **Não executar como procedimento padrão**; tratar como teste. |

**Autonomia**

| Nível | Significado |
|---|---|
| **Executa** | Operação aplica e registra no histórico de alterações. |
| **Executa e comunica** | Operação aplica e informa o time no mesmo dia, com motivo e data de reavaliação. |
| **Precisa de aprovação** | Só executar após aprovação do negócio Webmotors. Envolve verba, conversão norte, escopo de produto ou testes. |

**Donos**

| Dono | Responsabilidade |
|---|---|
| **Performance** | Configuração de campanhas, lances, orçamento, segmentação, anúncios e negativas. |
| **Martech** | Tags, pixels, eventos e conversões implementados via Adobe Tags (Launch), incluindo Events API via Adobe Event Forwarding e eventos de SDK/MMP. |
| **Negócio Webmotors** | Definição de conversão norte, escopo de produto, prioridade de praças e categorias, aprovação de verba. |
| **Dados / CRM** | Listas de audiência (CDP/CRM), validação de qualidade pós-lead, receita por praça. |
| **Produto / UX** | Landing pages e funil pós-clique (web e app). |

---

## 2. Visão das contas

### WM | Comprar · 399-829-8994

**Papel:** núcleo de geração de demanda B2C para lojistas. Maior conta da operação, com cerca de 48% da verba do MCC de janeiro a agosto de 2026 (R$ 16,23M).
**Praças:** SP, RJ, RS e DF.
**Formatos:** Search (7 a 8 campanhas), Performance Max (Principal e Supressão ativas; Público CDP pausada em 17/08), Demand Gen e Vídeo apenas no flight sazonal Mega Feirão (julho, encerrado).
**Conversão de lance:** goal customizado `geral_fluxo-comprar_lead-pj` (Proposta, Financiamento e Agendamento).
**Estratégia:** CPA desejado em todas as campanhas. Sem valor de conversão configurado.
**Atenção agora:** alta de CPA em setembro/2026 com causa multicausal; perda de Impression Share por rank em Search; sobreposição entre as duas PMax.

### WM | Expansão · 721-883-1035

**Papel:** mesmo objetivo comercial do Comprar, em estados fora das quatro praças principais (MG, GO, BA, CE, PR e SC).
**Formatos:** Search (DSA principal responde por cerca de 60% do investimento de Search) e quatro PMax estaduais (MG, GO, BA, CE), todas limitadas pelo orçamento.
**Conversão de lance:** goal customizado "MCC - Expansão - Lead PJ (Site e App)".
**Atenção agora:** entre 65% e 73% das conversões do goal são eventos de simulação, não proposta. O CPA agregado baixo não representa necessariamente o resultado final.

### WM | Vender · 966-658-9621

**Papel:** pessoa física paga pelo próprio anúncio (não é compra de lead).
**Formatos:** Search (1 campanha ativa), PMax (1 ativa) e Demand Gen (desde 17/06).
**Conversão de lance:** "[MCC] Purchase - Vender + App 7D" em Search e PMax, sinal limpo e fechado com Purchase. A Demand Gen mistura metas intermediárias.
**Referências de CPA (jan–ago):** Search R$ 158,44 · PMax R$ 78,11 (R$ 64,83 em agosto) · Demand Gen R$ 34,13 agregado, com apenas cerca de 13% de Purchase.
**Atenção agora:** expansão da automação para intenções de compra, modelo e FIPE; governança de URLs muito reativa. A viabilidade econômica do modelo (custo por anúncio versus ticket médio) é uma questão de negócio em aberto.

### Webmotors | Santander Financiamentos · 903-694-1523

**Papel:** geração de simulações de financiamento. Registro de projeto: 70% a 80% dos leads de financiamento já chegam organicamente pelo fluxo Comprar, e a conta existe para validar se campanhas dedicadas se justificam.
**Formatos:** Search (tCPA R$ 5,47), PMax "Teste A sem CDP" (tCPA R$ 6,19) e Demand Gen (goal "Meta Simulação", tCPA R$ 4,15).
**Atenção agora:** PMax configurada para todos os países; Display habilitado dentro de Search; testes de CDP que não isolam a variável; volume concentrado em simulação, com leitura qualificada dependente de SimAprov e ProposalAprov.

---

## 3. Regras de ouro da operação

Estas regras valem para as quatro contas e têm precedência sobre qualquer item individual do playbook.

**R1. Uma alavanca por vez.** Não alterar orçamento, CPA desejado, meta de conversão, segmentação ou estrutura na mesma janela. Cada mudança precisa de leitura isolada.

**R2. Respeitar a janela de aprendizado.** Após mudança relevante em lance, orçamento ou meta de conversão, aguardar de 7 a 14 dias antes de nova intervenção. O Google indica que a calibração pode levar até cerca de 50 eventos de conversão ou 3 ciclos de conversão.

**R3. Orçamento sobe em degraus de 10% a 20%.** Ciclos de 50% a 100% foram um dos fatores confirmados da alta de CPA de setembro/2026 no Comprar.

**R4. Nunca mexer em orçamento e CPA desejado ao mesmo tempo.** Em setembro/2026, cinco rodadas de alteração de CPA desejado em sete dias, sempre nas nove campanhas juntas, deixaram o CPA real travado entre R$ 29,75 e R$ 31,35 mesmo com três cortes seguidos de meta.

**R5. Rank e qualidade antes de verba.** Quando a perda de Impression Share por classificação supera a perda por orçamento, mais verba não resolve. Corrigir Ad Strength, relevância e destino primeiro.

**R6. Avaliar pelo CPA da conversão norte.** CPA agregado de metas que misturam simulação, proposta e compra não é indicador de resultado de negócio.

**R7. Comparar CPA apenas entre campanhas equivalentes.** Mesmo goal e mesma estratégia de lance. Vídeo com CPM desejado, Demand Gen com metas padrão da conta e Search com CPA desejado não são comparáveis diretamente.

**R8. Descartar os últimos 4 a 7 dias em leituras de CPA do Comprar.** O atraso de atribuição infla artificialmente o CPA recente.

**R9. Em PMax e Demand Gen, ler custo e CPA por canal, nunca share de impressão.** No Comprar, YouTube tem mais da metade das impressões da PMax e cerca de um quarto do custo.

**R10. Always On e sazonal são lidos separadamente.** Setembro tem padrão sazonal confirmado em 2025 e 2026 (alta de CPA a partir do dia 12). Feirões alteram intenção e taxa de conversão.

**R11. Hipótese não vira procedimento.** Só itens com status Executado ou Confirmado entram na rotina. Hipóteses entram no backlog de testes (seção 6).

**R12. Tag e evento são do Martech.** Qualquer ajuste de pixel, evento ou disparo de conversão é executado pelo time de Martech via Adobe Tags. A operação de mídia ajusta apenas a configuração das ações dentro do Google Ads.

**R13. Janelas sensíveis pedem cautela.** Eleições, Black Friday e janeiro/13º salário não são janelas para mudanças estruturais de risco.

**R14. Toda mudança é registrada.** Data, conta, campanha, o que mudou, motivo, métrica de sucesso e data de reavaliação.

---

## 4. Playbook por situação

### 4.1 Sinal de conversão e mensuração · `CONV`

#### CONV-01 · CPA baixo, mas a maior parte das conversões é evento intermediário

**Situação** — O CPA da campanha está abaixo ou perto do alvo, mas quando se abre a composição, eventos de simulação, modalidade ou checkout dominam o volume, e a conversão final (proposta, Purchase, aprovação) é minoria.

**Diagnóstico** — A meta usada para lances mistura etapas de funil com dificuldades diferentes. O Smart Bidding atinge o CPA desejado priorizando o evento mais fácil e volumoso. O CPA está tecnicamente correto, mas não mede o resultado de negócio. Ponto técnico importante: em **metas personalizadas** (custom goals), todas as ações incluídas entram no lance mesmo que estejam marcadas como secundárias. Para tirar um evento do lance, é preciso removê-lo da meta, não só marcá-lo como secundário.

**Como verificar** — Campanha → Segmentar → Conversões → Ação de conversão. Calcular o share de cada grupo (Proposta, Simulação, Agendamento, Purchase, SimAprov). Conferir em Configurações → Metas quais ações compõem a meta da campanha.

**Recomendação** — Definir com o negócio a conversão norte de cada conta. Manter microconversões como observação, fora da meta de lance. Após a troca, recalibrar o CPA desejado a partir de um novo baseline, sem transportar o alvo antigo. Se o evento intermediário precisar continuar no lance por volume, testar ponderação por valor em etapa posterior.

**Guardrail** — O volume de conversões reportado vai cair após a troca. Comunicar antes ao negócio que é mudança de métrica, não de performance. Prever de 2 a 4 semanas de reaprendizado. Não aumentar orçamento na mesma janela.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Expansão (Search e PMax: 65–73% simulação) · Santander (Search, PMax, DG: simulação domina) · Vender DG (13% Purchase) · Comprar (revisar as 5 ações do goal PJ) | 🟡 Em avaliação | Alta | Precisa de aprovação | Negócio Webmotors + Performance |

**Referência Google** — [Sobre ações de conversão principais e secundárias](https://support.google.com/google-ads/answer/11461796) · [Sobre metas de conversão específicas da campanha](https://support.google.com/google-ads/answer/9143218)

**Evidência interna** — Auditoria WM | Expansão (Search), tópico 1 · Auditoria WM | Expansão (PMax), tópico 1 · Auditoria Santander Financiamentos (Search, PMax e Demand Gen) · Auditoria WM | Vender (Demand Gen), tópico 2 · Auditoria WM | Comprar (Search), hipótese H19

---

#### CONV-02 · Campanha usando "metas padrão da conta" em vez de meta específica

**Situação** — A coluna Conversões da campanha contém ações de outros produtos (Vender, Assinaturas) ou de etapas não relacionadas ao objetivo dela.

**Diagnóstico** — A campanha está configurada para usar as metas padrão da conta. Nesse modo, toda ação marcada como principal em uma meta padrão entra no lance, sem filtro por produto. Na Demand Gen do Mega Feirão (Comprar), 4,8% das conversões eram de Vender e Assinaturas, e o CPA de R$ 5,84 ficou incomparável com o resto da conta.

**Como verificar** — Campanha → Configurações → Metas. Se aparecer "Usar metas padrão da conta", o problema existe. Confirmar com Segmentar → Ação de conversão.

**Recomendação** — Trocar para meta específica da campanha com as ações do funil do produto (no Comprar, `geral_fluxo-comprar_lead-pj` ou uma meta dedicada de Demand Gen com ações do funil Comprar). Aplicar antes de qualquer reativação.

**Guardrail** — Campanhas ativas entram em aprendizado. Em campanhas pausadas, corrigir antes de reativar.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (Demand Gen Mega Feirão, pausada) · checagem obrigatória em qualquer campanha nova | 🟢 Confirmado | Alta | Executa e comunica | Performance |

**Referência Google** — [Sobre metas de conversão padrão da conta](https://support.google.com/google-ads/answer/4677036) · [Atualizar metas de conversão](https://support.google.com/google-ads/answer/13810904)

**Evidência interna** — Auditoria WM | Comprar (Demand Gen), achados DG-05 e DG-06

---

#### CONV-03 · Demand Gen com várias metas marcadas ao mesmo tempo

**Situação** — A própria interface exibe o aviso de que campanhas Demand Gen não devem misturar várias metas de conversão ao otimizar para conversões.

**Diagnóstico** — Na Demand Gen de Vender, "Adicionar ao carrinho", "Iniciar pagamento" e "[MCC] Purchase - Vender + App 7D" estão marcadas juntas. Modalidade e Checkout, mais frequentes, dominam o volume.

**Como verificar** — Campanha → Configurações → Metas. Verificar se há mais de uma meta marcada e se o aviso da plataforma aparece.

**Recomendação** — Manter uma única meta: Purchase Vender 7D ou Finalização do Anúncio, conforme o KPI oficial do negócio. Modalidade e Checkout ficam como observação. Criar leitura de CPA de Purchase separada do CPA agregado.

**Guardrail** — O CPA desejado atual (R$ 50) não deve ser mantido para uma meta mais profunda. Observar novo baseline antes de definir alvo e orçamento.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Demand Gen) | 🟢 Confirmado | Alta | Precisa de aprovação (escolha do KPI) | Negócio Webmotors + Performance |

**Referência Google** — [Sobre metas de conversão específicas da campanha](https://support.google.com/google-ads/answer/9143218) · aviso exibido na própria tela de metas da campanha

**Evidência interna** — Auditoria WM | Vender (Demand Gen), tópico 2

---

#### CONV-04 · Composição de conversão depende de eventos de app com discrepância conhecida

**Situação** — Uma campanha parece ter composição de conversão muito favorável, mas grande parte do volume vem de eventos de app (`adj_*`).

**Diagnóstico** — Na PMax do Comprar, 60% das conversões são propostas enviadas pelo app (`adj_enviopropostatotalpj_android` e `_ios`). Existe discrepância registrada de até 100% entre Firebase e Adjust. Se esses eventos estiverem inflados, a qualidade aparente da campanha também está.

**Como verificar** — Segmentar por Ação de conversão e somar o peso dos eventos `adj_*`. Comparar a contagem com Firebase/GA4 no mesmo período.

**Recomendação** — Não usar a composição como argumento de qualidade até o Martech validar a contagem dos eventos de proposta via app.

**Guardrail** — Não remover os eventos de app do lance sem essa validação. A decisão depende do diagnóstico de tracking.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (PMax) · Expansão (propostas via app no goal) | 🔵 Hipótese | Média | Precisa de aprovação | Martech |

**Referência Google** — Não se aplica (validação de implementação).

**Evidência interna** — Auditoria WM | Comprar (PMax), tópico 4 · registro de desafios do projeto (discrepância Firebase × Adjust)

---

#### CONV-05 · Ação de conversão com alerta de diagnóstico ou função indefinida

**Situação** — Na tela de conversões, alguma ação aparece com status de atenção, sem pings recentes ou com alerta de tracking. Ou existe uma ação cuja função no funil ninguém sabe explicar.

**Diagnóstico** — Casos mapeados: (1) `lead_comprar_cdp` é importada via correspondência de cliques, está na categoria "Compras" em vez de "Lead", usa valor padrão de R$ 1 quando não recebe valor real, e as conversões otimizadas estão com status "Precisa de atenção". Sua função como métrica de qualidade de lead não foi confirmada. (2) A ação mapeada na categoria "Contatos" tem alerta de tracking ativo.

**Como verificar** — Metas → Conversões → Resumo. Coluna de status e diagnóstico de cada ação. Abrir a ação e conferir origem, categoria, valor e conversões otimizadas.

**Recomendação** — Manter `lead_comprar_cdp` como observação, fora de qualquer meta de lance, até o negócio confirmar função e critérios de qualificação. Martech corrige conversões otimizadas e investiga o alerta em "Contatos". Revisar a categoria da ação depois da definição.

**Guardrail** — Não promover o CDP a métrica de lance nem a KPI de relatório antes da validação.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (MCC) · qualquer conta que compartilhe as ações | 🟡 Em avaliação | Média | Precisa de aprovação | Martech + Negócio Webmotors |

**Referência Google** — [Sobre ações de conversão principais e secundárias](https://support.google.com/google-ads/answer/11461796)

**Evidência interna** — Auditoria WM | Comprar (Search), achados sobre CDP e hipótese H20 · Auditoria WM | Comprar (Demand Gen), learning sobre metas padrão

---

#### CONV-06 · Conta sem valor de conversão

**Situação** — A coluna Valor de conversão está zerada na conta inteira e a única estratégia possível é CPA desejado.

**Diagnóstico** — Sem valor, o algoritmo trata todas as conversões como equivalentes e não existe Maximizar valor nem ROAS desejado. No Comprar, o valor é R$ 0,00 em 100% das linhas analisadas. Ao dobrar a verba entre janeiro e março, o Google só podia buscar mais unidades ao mesmo custo alvo, o que é compatível com o degrau de CPA observado.

**Como verificar** — Adicionar a coluna Valor de conversão na visão de campanhas. Conferir a configuração de valor de cada ação em Metas → Conversões.

**Recomendação** — Definir com o negócio valores proxy por tipo de conversão (por exemplo, Proposta vale mais que Financiamento). Implementar via valor no evento ou importação offline. Só depois avaliar estratégias baseadas em valor.

**Guardrail** — Projeto estrutural. Não trocar estratégia de lance na mesma janela da implementação do valor.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar · avaliar Expansão | 🟡 Em avaliação | Média | Precisa de aprovação | Negócio Webmotors + Martech |

**Referência Google** — [Sobre valores de conversão](https://support.google.com/google-ads/answer/13064207)

**Evidência interna** — Media Snapshot #1, investigação INV-09

---

### 4.2 Lances, orçamento e aprendizado · `LANCE`

#### LANCE-01 · CPA subiu logo após rodadas de alteração de orçamento ou de CPA desejado

**Situação** — O CPA piora e não volta mesmo com cortes sucessivos de meta. O status de lance aparece repetidamente como "Aprendizagem".

**Diagnóstico** — O algoritmo não teve tempo de estabilizar entre mudanças. Em setembro/2026 no Comprar: orçamento +47,8% em três ciclos (04, 13 e 17/09), cinco rodadas de CPA desejado em sete dias (13 a 19/09) aplicadas nas nove campanhas juntas, somadas a sazonalidade e a um asset group fraco que absorveu o incremento de verba.

**Como verificar** — Ferramentas → Histórico de alterações, filtrado por Orçamento e Estratégia de lance. Status da estratégia de lance na coluna de status. Comparar com o mesmo período do ano anterior.

**Recomendação** — Congelar novas alterações por 7 a 14 dias. Seguir as regras R1 a R4. Se precisar ajustar, fazer em uma campanha ou em um grupo pequeno, nunca nas nove de uma vez.

**Guardrail** — Evitar movimentos grandes na segunda metade do mês, quando sobra pouco tempo de aprendizado antes do fechamento.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Todas as contas · evento confirmado no Comprar | 🟢 Confirmado | Alta | Precisa de aprovação (acima de 20%) | Performance |

**Referência Google** — [Duração do período de aprendizado](https://support.google.com/google-ads/answer/13020501) · [Sobre ações de conversão principais e secundárias](https://support.google.com/google-ads/answer/11461796) (nota sobre fase de aprendizado de 7 a 14 dias)

**Evidência interna** — Matriz de Risco — Aumento de CPA (WM | Comprar), fatores 1.1, 1.2 e 3

---

#### LANCE-02 · Campanha "limitada pelo orçamento", mas perdendo mais Impression Share por rank

**Situação** — A interface sinaliza limitação por orçamento e sugere mais verba, mas a perda de IS por classificação é igual ou maior que a perda por orçamento.

**Diagnóstico** — O gargalo é Ad Rank (qualidade, relevância, destino), não verba. Mais orçamento compra mais do mesmo inventário sem recuperar o que se perde por rank. No Comprar, entre 13–16/09 e 17–20/09, a perda por rank em Search subiu para 40,31% enquanto a perda por orçamento caiu. Em Vender, a Webmotors tem o maior IS do leilão, mas perde a disputa direta de posição para OLX em 53% e para Mercado Livre em 56% dos casos.

**Como verificar** — Adicionar as colunas Parcela de impressões perdidas na rede de pesquisa (classificação) e (orçamento) por campanha. Abrir Informações sobre leilões e observar "Taxa de classificação superior".

**Recomendação** — Priorizar os itens QUAL-01 a QUAL-03 antes de pedir verba. Em PMax do Comprar, onde a perda por orçamento domina no posicionamento de pesquisa, mais verba tem efeito real e pode ser considerada.

**Guardrail** — O relatório de leilão da PMax cobre apenas o inventário de pesquisa, sem Display, YouTube, Discover ou Gmail.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (Search) · Vender (Search) · Santander (Search) · Expansão (validar após limpeza do sinal) | 🟢 Confirmado | Alta | Executa (diagnóstico) · Precisa de aprovação (verba) | Performance |

**Referência Google** — [Dados de parcela de impressões](https://support.google.com/google-ads/answer/7103314)

**Evidência interna** — Auditoria WM | Comprar (Search), hipótese H21 · Matriz de Risco — Aumento de CPA, fator 4 · Auditoria WM | Vender (Search), tópicos 1, 2 e 6

---

#### LANCE-03 · Ajustes manuais de lance em campanhas com Smart Bidding

**Situação** — Existem ajustes de lance por localização, audiência ou dados demográficos em campanhas com CPA desejado, ou alguém propõe criar esses ajustes como otimização.

**Diagnóstico** — Sob Smart Bidding, a maior parte dos ajustes manuais não é aplicada, porque o algoritmo já considera localização, dispositivo e contexto em cada leilão. As exceções são o ajuste de dispositivo em CPA desejado (que altera o alvo, não o lance) e a exclusão de dispositivo a -100%. Casos mapeados: ajuste de +20% em bairros de São Paulo na campanha `modelos-diversos` do Comprar; propostas de ajuste por audiência Customer AI e por gênero e idade em auditorias anteriores.

**Como verificar** — Campanha → Locais, Públicos e Dados demográficos → coluna Ajuste de lance. Conferir a estratégia de lance da campanha.

**Recomendação** — Não usar ajuste de lance como alavanca em campanhas com Smart Bidding. As alavancas reais são: exclusão (segmentação), campanha ou grupo separado com orçamento e alvo próprios, sinal de audiência, ou meta de CPA por dispositivo.

**Guardrail** — Remover ajustes existentes não muda a entrega, mas limpa a leitura. Não tratar como otimização com ganho esperado.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Todas as contas | 🟢 Confirmado | Média | Executa | Performance |

**Referência Google** — [Sobre o Smart Bidding](https://support.google.com/google-ads/answer/7065882)

**Evidência interna** — Registro da conta WM | Comprar (ajuste +20% em bairros) · Auditoria WM | Vender (Search), tópico 12

---

#### LANCE-04 · Metas de CPA por segmento muito distantes do histórico

**Situação** — Grupos ou segmentos com CPA desejado que nunca é atingido convivem com outros cujo alvo fica próximo do realizado.

**Diagnóstico** — Na campanha `marcas_sp` do Comprar, alvos de R$ 10 a R$ 15 nunca são atingidos (Toyota estoura em +120%, Chevrolet em +61%), enquanto alvos de R$ 23 ficam próximos do realizado. Alvo muito abaixo do histórico restringe a entrada em leilões.

**Como verificar** — Relatório da estratégia de lance: comparar CPA desejado médio com CPA real por grupo nos últimos 30 dias.

**Recomendação** — Recalibrar alvos para perto do CPA realizado e ajustar gradualmente. Testar lances diferenciados entre termos genéricos e de modelo dentro do mesmo grupo (ver backlog T-08).

**Guardrail** — Aplicar em lotes pequenos, seguindo a R1.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (`marcas_sp`) | 🟢 Confirmado | Média | Executa e comunica | Performance |

**Referência Google** — [Duração do período de aprendizado](https://support.google.com/google-ads/answer/13020501)

**Evidência interna** — Auditoria WM | Comprar (Search), hipótese H11

---

#### LANCE-05 · Campanha eficiente limitada pelo orçamento com espaço para escalar

**Situação** — Campanha com sinal de conversão limpo, CPA recente no alvo ou abaixo dele e status "limitada pelo orçamento".

**Diagnóstico** — Há espaço de escala, mas o histórico mostra que expansões agressivas reabrem inventário marginal. Na PMax de Vender, o CPA ficou acima de R$ 90 entre março e maio, antes de voltar para R$ 64,83 em agosto (alvo de R$ 70).

**Como verificar** — Coluna Parcela de impressões perdida por orçamento. Simulador de orçamento no relatório da estratégia de lance. CPA da conversão norte nas últimas 4 semanas.

**Recomendação** — Escalar em degraus de 10% a 20%, mantendo o CPA desejado fixo em cada janela. Definir antes o gatilho de reversão (por exemplo, CPA da conversão norte acima da faixa aceitável por uma janela completa de leitura).

**Guardrail** — Em Santander, só escalar se a eficiência se sustentar em SimAprov ou ProposalAprov, não apenas em simulação.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (PMax) · Santander (Demand Gen e PMax, após GEO-02 e HIG-02) | 🟢 Confirmado | Média | Precisa de aprovação | Performance + Negócio Webmotors |

**Referência Google** — [Duração do período de aprendizado](https://support.google.com/google-ads/answer/13020501)

**Evidência interna** — Auditoria WM | Vender (PMax), tópico 6 · Auditoria Santander Financiamentos (Demand Gen), tópico 6

---

#### LANCE-06 · Evento sazonal curto ou falha de tracking afetando o aprendizado

**Situação** — Feirão, promoção relâmpago ou data comercial com alta esperada de conversão. Ou um período em que o tracking falhou e as conversões ficaram subnotificadas.

**Diagnóstico** — O Smart Bidding já considera sazonalidade recorrente, mas não reage bem a eventos curtos e atípicos nem a dados corrompidos.

**Como verificar** — Calendário comercial da Webmotors. Para falhas de tracking, queda abrupta de conversões sem queda equivalente de cliques.

**Recomendação** — Para eventos de 1 a 7 dias com mudança brusca de taxa de conversão, usar ajuste de sazonalidade. Para falhas de tracking, aplicar exclusão de dados cobrindo também os dias anteriores equivalentes ao atraso de conversão. Reportar sazonal separado do Always On.

**Guardrail** — Não usar ajuste de sazonalidade em eventos longos. Não usar exclusão de dados para "apagar" períodos de performance ruim real.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Todas as contas | 🟢 Confirmado | Média | Executa e comunica | Performance (com Martech em falhas de tracking) |

**Referência Google** — [Ajustes de sazonalidade](https://support.google.com/google-ads/answer/10369906) · [Novos recursos de PMax: ajustes de sazonalidade e exclusões de dados](https://support.google.com/google-ads/answer/12351101)

**Evidência interna** — Matriz de Risco — Aumento de CPA, fator 3 (sazonalidade de setembro) · Auditoria WM | Vender (PMax), tópico 11

---

### 4.3 Segmentação geográfica e idioma · `GEO`

#### GEO-01 · Campanhas regionais com "Presença ou interesse"

**Situação** — O relatório de localização mostra gasto fora das UFs segmentadas, ou a campanha está configurada com a opção padrão de local.

**Diagnóstico** — "Presença ou interesse" alcança também pessoas fora da praça que demonstraram interesse por ela. Para aquisição dentro de praças definidas, a opção coerente é "Presença". Na PMax da Expansão, cerca de R$ 20,2 mil (1,89%) foram gastos fora das quatro UFs-alvo, com SP concentrando R$ 16,4 mil.

**Como verificar** — Campanha → Configurações → Locais → Opções de local. Relatório Onde seus anúncios foram exibidos, visão por local correspondente.

**Recomendação** — Trocar para "Presença: pessoas que estão ou costumam estar nos locais segmentados". Reextrair o relatório de localização de 7 a 14 dias depois para medir o efeito.

**Guardrail** — Em Vender, testar Search e PMax em janelas diferentes para isolar o efeito de cada um. Não combinar com outras mudanças na mesma janela.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar ✅ (PMax e Search SP, 16/09; efeito neutro confirmado) · Expansão (Search e PMax, pendente) · Vender (Search e PMax, pendente; Demand Gen já usa Presença) | ✅ Comprar · 🟢 demais | Alta | Executa e comunica | Performance |

**Referência Google** — [Sobre a segmentação por locais geográficos](https://support.google.com/google-ads/answer/2453995)

**Evidência interna** — Auditoria WM | Expansão (Search), tópico 4 · Auditoria WM | Expansão (PMax), tópico 3 · Auditoria WM | Vender (Search e PMax), seção Location · Matriz de Risco, fator 2.3 · página 11 — Recomendações e Quick Wins

---

#### GEO-02 · Campanha segmentada para "Todos os países e territórios"

**Situação** — Parte relevante das impressões e cliques vem de fora do Brasil.

**Diagnóstico** — Na PMax "Teste A" de Santander, R$ 7.937,57 foram investidos fora do Brasil: 3,55% da verba, mas 49,8% das impressões e 15,6% dos cliques, para 0,62% das conversões. O CPA internacional é cerca de 6 vezes o brasileiro.

**Como verificar** — Campanha → Configurações → Locais. Relatório de localização por país.

**Recomendação** — Restringir a localização ao Brasil com a opção "Presença". Monitorar de 7 a 14 dias para separar ganho de eficiência de perda de volume.

**Guardrail** — Nenhum; é correção de erro.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Santander (PMax) · checagem obrigatória em qualquer campanha nova | 🟢 Confirmado | Alta | Executa e comunica | Performance |

**Referência Google** — [Sobre a segmentação por locais geográficos](https://support.google.com/google-ads/answer/2453995)

**Evidência interna** — Auditoria Santander Financiamentos (PMax), tópico 1

---

#### GEO-03 · Exclusões geográficas diferentes entre campanhas que deveriam ser espelhadas

**Situação** — Campanhas com o mesmo papel têm regras de exclusão de local distintas.

**Diagnóstico** — Nas PMax da Expansão, GO, BA e CE têm exclusões geográficas e MG não tem nenhuma. No Comprar, CE, BA e GO foram retiradas das exclusões das PMax em 16/09. As exclusões podem reduzir sobreposição entre contas, mas não substituem o ajuste da opção principal de local.

**Como verificar** — Campanha → Locais → Excluídos. Comparar entre campanhas do mesmo papel e entre as contas Comprar e Expansão.

**Recomendação** — Padronizar uma regra de exclusão por papel de campanha, documentada. Definir com o negócio se Comprar e Expansão devem ter praças mutuamente exclusivas.

**Guardrail** — Aplicar depois de GEO-01, em janela própria.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Expansão (PMax MG) · Comprar × Expansão | 🟡 Em avaliação | Média | Precisa de aprovação (regra entre contas) | Performance + Negócio Webmotors |

**Referência Google** — [Sobre a segmentação por locais geográficos](https://support.google.com/google-ads/answer/2453995)

**Evidência interna** — Auditoria WM | Expansão (PMax), tópico 3 · Auditoria WM | Comprar (PMax), data de corte

---

#### GEO-04 · Anúncios dinâmicos (DSA) configurados em inglês

**Situação** — Nas configurações de DSA da campanha, o idioma do domínio está como "Inglês".

**Diagnóstico** — O site webmotors.com.br não tem conteúdo em inglês. O idioma do DSA precisa corresponder ao idioma das páginas. O erro reduz o controle sobre títulos gerados e, combinado com AI Max, tende a gerar anúncios de qualidade inferior.

**Como verificar** — Campanha → Configurações → Configuração de anúncios dinâmicos de pesquisa → Idioma.

**Recomendação** — Alterar para Português. Custo e risco praticamente zero.

**Guardrail** — Nenhum. No Comprar, a correção foi avaliada e descartada como causa da alta de CPA de setembro.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar ✅ (16/09) · Expansão (6 campanhas genéricas estaduais) · Vender (campanha Search ativa) | ✅ Comprar · 🟢 demais | Alta | Executa | Performance |

**Referência Google** — [Como corrigir baixo tráfego em anúncios dinâmicos de pesquisa (domínio e idioma)](https://support.google.com/sa360/answer/9797935)

**Evidência interna** — Auditoria WM | Comprar (Search), Quick Wins · Auditoria WM | Expansão (Search), tópico 3 · Auditoria WM | Vender (Search), tópico 3 · Matriz de Risco, fator 2.1

---

#### GEO-05 · Campanha configurada para "Todos os idiomas"

**Situação** — O idioma da campanha está em "Todos os idiomas", em operação 100% voltada ao Brasil.

**Diagnóstico** — Amplia a elegibilidade para usuários com interface em outros idiomas. Isoladamente não comprova desperdício, mas soma mais uma camada de abertura a campanhas que já usam correspondência ampla e AI Max.

**Como verificar** — Campanha → Configurações → Idiomas. Relatório de termos de pesquisa para procurar consultas em outros idiomas.

**Recomendação** — Se não houver volume qualificado em outros idiomas, definir Português como padrão de conta e documentar.

**Guardrail** — Item de higiene, não de performance. Acompanhar volume e CPA após o ajuste.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Santander (Search) · Vender (PMax) | 🟢 Confirmado | Baixa | Executa e comunica | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria Santander Financiamentos (Search), tópico 9 · Auditoria WM | Vender (PMax), tópico 9

---

#### GEO-06 · CPA muito diferente entre estados em campanha nacional com CPA desejado

**Situação** — O relatório de localização mostra variação grande de CPA entre UFs, e alguém propõe ajuste de lance por estado.

**Diagnóstico** — Em Vender, Santa Catarina é o pior estado tanto em Search (R$ 208,66) quanto em PMax (R$ 109,05). Em Search, a diferença entre o melhor e o pior estado chega a 2,6 vezes. Ajuste de lance por local não funciona sob CPA desejado (ver LANCE-03), e PMax não aceita ajuste manual de lance.

**Como verificar** — Relatório de localização filtrado por estados com pelo menos 20 conversões, para não concluir sobre ruído.

**Recomendação** — Seguir a sequência: (1) aplicar GEO-01 e esperar 7 a 14 dias; (2) validar receita ou ticket por estado com CRM/BI; (3) só então decidir entre excluir o local ou isolar em campanha própria com orçamento e alvo dedicados.

**Guardrail** — Campanha separada só se sustenta com volume suficiente para aprendizado estável. Santa Catarina tem cerca de 26 conversões por mês em Search. CPA alto não é resultado ruim se o ticket compensar.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Search e PMax) | 🟡 Em avaliação | Média | Precisa de aprovação | Performance + Dados / CRM |

**Referência Google** — [Sobre o Smart Bidding](https://support.google.com/google-ads/answer/7065882)

**Evidência interna** — Auditoria WM | Vender (Search), tópico 12 · Auditoria WM | Vender (PMax), tópico 13

---

### 4.4 Rede e inventário · `REDE`

#### REDE-01 · Rede de Display habilitada dentro de campanha de Search

**Situação** — Ao segmentar a campanha de Search por rede, aparece custo em "Rede de Display".

**Diagnóstico** — A opção de expansão para Display está marcada nas configurações de rede. Display opera em contexto de navegação, sem busca ativa, e entrega conversões mais rasas. Casos mapeados: nas 6 estaduais da Expansão, CPA 47,9% maior que Google Search e o menor share de Proposta (23,8%). Em Santander, CPA quase 3 vezes maior e nenhuma conversão chegando a ProposalAprov.

**Como verificar** — Campanha → Segmentar → Rede (com parceiros de pesquisa). Configurações → Redes.

**Recomendação** — Desmarcar "Rede de Display" nas campanhas de Search. Se houver interesse estratégico em Display, tratar como campanha própria, com audiência, criativo e KPI específicos.

**Guardrail** — Nenhum relevante. No Comprar, a remoção foi avaliada e descartada como causa da alta de CPA (Display já estava praticamente sem gasto desde 07/09).

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar ✅ · Expansão (6 genéricas estaduais) · Santander (Search) | ✅ Comprar · 🟢 demais | Alta | Executa e comunica | Performance |

**Referência Google** — [Sobre a Expansão para Display em campanhas de pesquisa](https://support.google.com/google-ads/answer/7193800)

**Evidência interna** — Auditoria WM | Comprar (Search), seção Network · Auditoria WM | Expansão (Search), tópico 6 · Auditoria Santander Financiamentos (Search), tópico 8 · Matriz de Risco, fator 2.2

---

#### REDE-02 · Decidir se mantém ou desliga parceiros de pesquisa

**Situação** — Parceiros de pesquisa estão ativos e surge a dúvida se devem ser desligados.

**Diagnóstico** — Não existe regra única entre as contas. No Comprar (campanhas com Display), parceiros de pesquisa entregam share de Proposta de cerca de 64,8%, **acima** do Google Search (58,7%): é o inventário de maior qualidade relativa nesse cenário. Na Expansão, entregam CPA de 13% a 20% maior e share de Proposta 6 a 7 pontos abaixo do Google Search, mas com volume abaixo de 0,7% do grupo. Em Vender, não há recorte por rede.

**Como verificar** — Campanha → Segmentar → Rede (com parceiros de pesquisa), cruzado com Segmentar → Ação de conversão. Olhar custo, CPA e share da conversão norte.

**Recomendação** — Comprar: **manter**. Expansão: baixa prioridade; reavaliar depois que o sinal de conversão for corrigido (CONV-01). Vender: fazer o recorte por rede e Purchase antes de decidir.

**Guardrail** — Não aplicar o desligamento em lote entre contas.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (manter) · Expansão · Vender | 🟢 Confirmado (Comprar e Expansão) · 🔵 Vender | Baixa | Executa e comunica | Performance |

**Referência Google** — Não mapeada. Usar a segmentação nativa "Rede (com parceiros de pesquisa)".

**Evidência interna** — Auditoria WM | Comprar (Search), seção Network, leitura 3 · Auditoria WM | Expansão (Search), tópico 6 · Auditoria WM | Vender (Search), tópico 9

---

#### REDE-03 · Lista de exclusão de placements ausente ou com critério desconhecido

**Situação** — O relatório de placements automáticos mostra apps de jogos, sites fora do idioma ou inventário sem conversão. Ou existem exclusões em nível de conta cujo critério ninguém sabe explicar.

**Diagnóstico** — No Vídeo do Comprar, apps de jogos e sites estrangeiros apareceram com 0% de conversão na amostra, concentrados em Display. As três listas existentes cobrem apenas contexto político, apps e brand safety. No sentido oposto, a lista de placements excluídos da conta Comprar inclui veículos como Jovem Pan (site e dois canais de YouTube) sem critério documentado. Exclusões de placement em nível de conta também se aplicam à rede de parceiros de pesquisa e são respeitadas pela PMax.

**Como verificar** — Campanhas → Públicos-alvo, palavras-chave e conteúdo → Conteúdo → Exclusões. Ferramentas → Adequação do conteúdo → Placements excluídos. Relatório de placements (onde os anúncios foram exibidos) em Vídeo, Demand Gen e PMax.

**Recomendação** — Construir lista de exclusão de placements de baixa qualidade em nível de conta, reaplicável a qualquer campanha de Vídeo, Display, Demand Gen e PMax. Revisar a lista existente e confirmar internamente se os critérios ainda fazem sentido.

**Guardrail** — Como exclusões de conta afetam também parceiros de pesquisa, revisar o impacto antes de ampliar listas.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (criar lista de baixa qualidade · revisar exclusões existentes) · aplicável a todas | 🟢 Confirmado (lacuna) · 🟡 Em avaliação (revisão de exclusões) | Média | Executa e comunica (novas) · Precisa de aprovação (remover existentes) | Performance + Negócio Webmotors |

**Referência Google** — [Excluir páginas da web e vídeos específicos](https://support.google.com/google-ads/answer/2454012) · [Recursos de adequação da marca na Performance Max](https://support.google.com/google-ads/answer/13607727)

**Evidência interna** — Auditoria WM | Comprar (Video), tópico 4 · página 11 — Recomendações e Quick Wins (placements excluídos)

---

#### REDE-04 · Vídeo com parte relevante do orçamento em Display

**Situação** — Em campanha de Vídeo, Display consome parcela grande do orçamento e entrega poucas visualizações.

**Diagnóstico** — No Vídeo do Mega Feirão (Comprar), Display consumiu 35,9% do orçamento e entregou 12,8% das views. O custo por visualização completa foi 3,76 vezes o do YouTube. Não é ausência de retorno (houve 229 mil views), é ineficiência de mix.

**Como verificar** — Campanha de Vídeo → Segmentar → Rede. Comparar CPV e taxa de visualização por rede.

**Recomendação** — Reduzir a expansão para Display em etapas (por exemplo, 80/20 para YouTube) antes do corte total, confirmando que o CPV do YouTube se mantém estável com mais verba.

**Guardrail** — A campanha usa CPM desejado (otimiza alcance, não conversão). Avaliar por CPV e visualizações completas, não por CPA.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (próximas campanhas de Vídeo sazonais) | 🟢 Confirmado | Média | Executa e comunica | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria WM | Comprar (Video), tópico 1

---

#### REDE-05 · Leitura de canais em PMax e Demand Gen

**Situação** — Alguém propõe cortar YouTube, Display ou Gmail da PMax por "vazamento de verba".

**Diagnóstico** — Em PMax, a distribuição por canal é automática. Volume de impressão não indica para onde vai a verba: no Comprar, YouTube tem 52% a 57% das impressões e 24% a 25% do custo, enquanto Search concentra cerca de 65% do custo. Em Vender, Gmail tem CPA de cerca de R$ 279, mas representa cerca de 1% do investimento.

**Como verificar** — PMax → Insights → Relatório de distribuição por canal. Comparar share de custo e CPA por canal, e composição de conversões por canal.

**Recomendação** — Revisar mensalmente custo, CPA e composição por canal. Agir via exclusão de placements (REDE-03) e qualidade de assets, sem tentar equalizar canais manualmente.

**Guardrail** — O relatório por canal pode somar mais que o total da campanha por sobreposição de contagem entre canais. Isso é comportamento conhecido, não erro de dado.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar · Expansão · Vender · Santander (PMax) | 🟢 Confirmado | Baixa | Executa | Performance |

**Referência Google** — [Novidades em campanhas Performance Max](https://support.google.com/google-ads/answer/13311048)

**Evidência interna** — Auditoria WM | Comprar (PMax), tópico 3 · Auditoria WM | Expansão (PMax), tópico 2 · Auditoria WM | Vender (PMax), tópicos 3 e 8

---

### 4.5 Intenção de busca, automação e destinos · `INT`

#### INT-01 · Termos de pesquisa fora do objetivo da campanha

**Situação** — O relatório de termos mostra consultas de outro produto ou fora do escopo comercial, geradas por AI Max, DSA ou correspondência ampla.

**Diagnóstico** — A automação interpreta o domínio Webmotors de forma mais ampla que o objetivo da campanha. Casos mapeados:
Vender recebe buscas de compra, modelo, estoque e FIPE ("nissan kicks 2020 1.6", "tabela fipe do prisma 2019").
Santander recebe financiamento imobiliário (a palavra-chave "simulador imobiliario" está ativa e gastou R$ 430 entre junho e agosto), marcas de bancos concorrentes (R$ 5,1 mil no período, vindas de ampla e de variações de frase), consórcio (R$ 15,2 mil), negativado/score (R$ 19,4 mil) e empréstimo/refinanciamento.
Comprar tem vazamento de busca de marca via ampla e AI Max, com custo 3,2 vezes a média de Search da conta.

**Como verificar** — Palavras-chave → Termos de pesquisa, com as colunas de tipo de correspondência e origem da correspondência (AI Max, palavra-chave, DSA). Agrupar os termos por cluster de intenção.

**Recomendação** — Manter uma taxonomia fixa de clusters por conta. Em Vender: venda direta · avaliação/FIPE com intenção de venda · compra/estoque · modelo puro · financiamento · concorrentes · informacional. Negativar em **listas compartilhadas temáticas** os clusters comprovadamente fora de escopo, em vez de negativas unitárias. Ações imediatas em Santander: pausar e negativar "simulador imobiliario" e negativar marcas de bancos concorrentes. Clusters que dependem de escopo de produto (moto, consórcio, negativado, refinanciamento) aguardam decisão do negócio.

**Guardrail** — Não desligar AI Max ou ampla por padrão. Medir primeiro o quanto ampliam consultas e com qual qualidade. FIPE pode indicar preparação para venda; não negativar o cluster inteiro sem ler a conversão. Negativa em lista compartilhada atinge todas as campanhas conectadas: revisar antes de aplicar.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Search) · Santander (Search) · Comprar (Search: marca) · Expansão (Search) | 🟢 Confirmado | Alta | Executa e comunica (fora de escopo evidente) · Precisa de aprovação (clusters de escopo de produto) | Performance + Negócio Webmotors |

**Referência Google** — [Sobre o AI Max para campanhas de pesquisa](https://support.google.com/google-ads/answer/15910187) · [Criar e aplicar listas de palavras-chave negativas](https://support.google.com/google-ads/answer/7449003)

**Evidência interna** — Auditoria WM | Vender (Search), tópicos 3 e 8 · Auditoria Santander Financiamentos (Search), tópicos 2 e 4 · Auditoria WM | Comprar (Search), principais findings

---

#### INT-02 · Milhares de exclusões de URL individuais

**Situação** — A campanha tem milhares de exclusões de URL do tipo "URL igual a...", e novas páginas indesejadas continuam aparecendo.

**Diagnóstico** — A expansão de URL final está ligada e a contenção é feita página a página. Num site com estoque dinâmico, a manutenção individual sempre fica atrás do crescimento do site. Em Vender, a campanha de Search tem cerca de 5,4 mil exclusões de URL e a PMax, milhares. Ponto técnico importante: **com a expansão de URL ligada, um feed de páginas orienta, mas não restringe** os destinos. Para restringir, é preciso desligar a expansão ou usar regras de exclusão.

**Como verificar** — Configurações → Otimização de recursos → Expansão de URL final e exclusões. Relatório de páginas de destino (onde o tráfego efetivamente chegou), não apenas a lista de exclusões.

**Recomendação** — Substituir exclusões unitárias por regras de diretório ou padrão de URL (áreas de Comprar, estoque, conteúdo, institucional). Avaliar feed de páginas com as URLs elegíveis do funil (por exemplo, vender-carro, vender-moto e etapas aprovadas). Revisar o relatório de páginas de destino mensalmente. Na DSA da Expansão, validar a origem de segmentação (todas as URLs, feed ou combinação) e revisar exclusões de categorias como editorial, FIPE, feirões e institucional.

**Guardrail** — Reduzir as exclusões exatas gradualmente, à medida que a regra estrutural passa a cobrir os casos.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Search e PMax) · Expansão (DSA) · Comprar (validar URLs da expansão na PMax) | 🟢 Confirmado | Alta | Executa e comunica | Performance |

**Referência Google** — [Como usar feeds de páginas na Performance Max](https://support.google.com/google-ads/answer/13568488) · [Sobre a expansão de URL final na Performance Max](https://support.google.com/google-ads/answer/14337539) · [Controles de URL e segmentação de pesquisa na Performance Max](https://support.google.com/google-ads/answer/16672777)

**Evidência interna** — Auditoria WM | Vender (Search), tópico 4 · Auditoria WM | Vender (PMax), tópico 4 · Auditoria WM | Expansão (Search), tópico 3 · Auditoria WM | Comprar (PMax), tópico 5

---

#### INT-03 · Termos de marca aparecendo em PMax apesar das listas de exclusão

**Situação** — O relatório de termos da PMax mostra buscas por "webmotors" e variações.

**Diagnóstico** — As listas "Brandmonitor Negativações" e "Exclusão Mobiauto e Icarros" estão configuradas, mas a cobertura é incompleta. Contexto de negócio: a ausência de campanha de marca dedicada é decisão deliberada (competição com o orgânico). O vazamento via automação não é.

**Como verificar** — PMax → Insights → Termos de pesquisa. Configurações → Exclusões de marca, conferindo quais listas estão aplicadas e o que contêm.

**Recomendação** — Auditar o conteúdo e a cobertura efetiva das listas de exclusão de marca em todas as PMax. Garantir que a marca Webmotors esteja excluída onde a decisão de negócio pede.

**Guardrail** — Não criar campanha de marca como "correção". A estratégia de marca depende do teste de incrementalidade (backlog T-01).

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (PMax) · verificar Expansão, Vender e Santander | 🟢 Confirmado | Alta | Executa e comunica | Performance |

**Referência Google** — [Sobre exclusões de marca](https://support.google.com/google-ads/answer/16669487) · [Aplicar exclusões de marca a campanhas](https://support.google.com/google-ads/answer/14505308)

**Evidência interna** — Auditoria WM | Comprar (PMax), tópico 5 · Auditoria WM | Comprar (Search), hipótese H13

---

#### INT-04 · Sitelinks e assets levando para jornadas laterais ou destino errado

**Situação** — Assets da campanha levam para estoque, institucional ou FAQ numa campanha de fundo de funil, ou um asset aponta para a página errada.

**Diagnóstico** — Em Vender: "Nosso Estoque" leva a /carros/estoque, "Categoria Institucional" a /institucional/, e **"Anuncie Aqui Sua Moto" aponta para /vender-carro, não para /vender-moto**. Também foram encontradas peças pausadas de Feirão com mensagem de Comprar ("financiar seu carro", "até 60x") dentro da campanha Vender.

**Como verificar** — Anúncios e recursos → Recursos → filtrar por sitelink. Relatório de associação de recursos (entrega por asset).

**Recomendação** — Corrigir imediatamente o sitelink de moto. Remover ou limitar "Nosso Estoque" e "Categoria Institucional" da estrutura Vender. Priorizar sitelinks como preços e planos, como anunciar, venda seu carro, venda sua moto e segurança para vender. Manter pelo menos seis sitelinks relevantes. Criar checklist para que anúncios de cada produto usem só a proposta de valor daquele produto.

**Guardrail** — O custo associado a um sitelink no relatório é o custo das impressões em que ele participou, não gasto incremental causado por ele.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Search) · checklist aplicável a todas | 🟢 Confirmado | Alta | Executa | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria WM | Vender (Search), tópicos 5 e 10

---

### 4.6 Qualidade e leilão · `QUAL`

#### QUAL-01 · Grupos com um único anúncio ou Ad Strength "Média" ou "Baixa"

**Situação** — Grupos de anúncios com apenas um RSA ativo, ou com eficácia do anúncio "Média" ou "Baixa". Em PMax, asset groups com eficácia entre "Média" e "Baixa".

**Diagnóstico** — Estrutura de um anúncio por grupo e assets de baixa qualidade reduzem Ad Rank e contribuem para a perda de IS por classificação. Em Vender, um único anúncio com eficácia "Média" concentra 93,4% do custo e 94,6% das conversões da campanha. No Comprar, há anúncios "Excelente" pausados enquanto anúncios "Média" seguem ativos.

**Como verificar** — Anúncios → coluna Eficácia do anúncio. Em PMax: Grupos de recursos → Eficácia.

**Recomendação** — Ter pelo menos dois RSAs com eficácia "Boa" ou "Excelente" por grupo. Seguir as ações sugeridas pela própria plataforma (mais títulos e descrições, uso de termos das palavras-chave, variedade). Revisar a composição de imagens, títulos, descrições e vídeos das PMax do Comprar e da Expansão.

**Guardrail** — A eficácia do anúncio não afeta diretamente a elegibilidade de veiculação. É um indicador de qualidade criativa, não uma meta em si.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (Search e PMax) · Expansão (PMax) · Vender (Search) | 🟢 Confirmado | Alta | Executa | Performance |

**Referência Google** — [Sobre a eficácia do anúncio em anúncios responsivos de pesquisa](https://support.google.com/google-ads/answer/9921843)

**Evidência interna** — Auditoria WM | Comprar (Search), Quick Wins · Estrutura de Mídia Ideal, tópico 5 · Auditoria WM | Vender (Search), tópico 6 · página 11 — Recomendações e Quick Wins

---

#### QUAL-02 · Assets reprovados sem redundância em nível de conta

**Situação** — Imagens reprovadas por texto sobreposto, assets de app reprovados por incompatibilidade de destino, sitelinks reprovados, sem assets de conta para cobrir.

**Diagnóstico** — Padrão repetido em Comprar, Expansão e Vender. Reduz os formatos elegíveis e o Ad Rank.

**Como verificar** — Anúncios e recursos → Recursos → filtrar por status "Reprovado" ou "Qualificado (limitado)". Conferir recursos em nível de conta.

**Recomendação** — Corrigir os assets reprovados e criar um conjunto de assets em nível de conta como redundância.

**Guardrail** — Nenhum relevante.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar · Expansão · Vender | 🟢 Confirmado | Média | Executa | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria WM | Vender (Search), tópico 5 · Estrutura de Mídia Ideal, tópico 5

---

#### QUAL-03 · Estrutura com grupos ou palavras-chave inertes

**Situação** — Campanhas com grande número de grupos zerados ou grupos com dezenas de palavras-chave ativas e nenhuma entrega.

**Diagnóstico** — Em `modelos-diversos_sp_search` (Comprar), há 1.263 grupos configurados, com apenas 4,2% ativos. Em Santander, os grupos Modelos (43 palavras-chave ativas) e Motos (74 ativas) não entregaram nada no período, enquanto o grupo Carro absorve essa intenção.

**Como verificar** — Grupos de anúncios → filtro por impressões = 0 no período. Comparar com os termos de pesquisa que chegam aos grupos que entregam.

**Recomendação** — Reestruturar os grupos para que tenham função real ou remover a complexidade que não gera controle nem leitura.

**Guardrail** — Mudança estrutural. Fazer dentro do desenho da estrutura ideal de conta, não isoladamente.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (`modelos-diversos`) · Santander (Modelos e Motos) | 🟢 Confirmado | Média | Precisa de aprovação | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria WM | Comprar (Search), principais findings · Auditoria Santander Financiamentos (Search), tópico 5

---

### 4.7 Estrutura e sobreposição · `EST`

#### EST-01 · Duas PMax com a mesma configuração e a mesma intenção

**Situação** — Duas campanhas PMax com a mesma meta, a mesma geografia, o mesmo asset group e grande sobreposição de termos de pesquisa.

**Diagnóstico** — No Comprar, a PMax Supressão foi criada em 28/04 como cópia da Principal. Tem o mesmo asset group, os mesmos 6 temas de pesquisa e 78% dos termos também presentes na Principal. A diferença real está só nas supressões de dados (perfis orgânicos, CRM, clientes PJ, bots). A incrementalidade da Supressão não foi comprovada. A piora de CPA da Principal começou antes da Supressão existir, então não há como atribuir causalidade.

**Como verificar** — Comparar configurações lado a lado (geografia, lance, asset group, temas, exclusões). Cruzar os relatórios de termos de pesquisa das duas campanhas.

**Recomendação** — Definir papéis mutuamente exclusivos para as duas campanhas ou rodar teste controlado de consolidação temporária (backlog T-02).

**Guardrail** — Durante o teste, não mudar CPA desejado, orçamento, geografia nem metas. Não criar uma terceira PMax "limpa": acrescenta mais uma camada de fragmentação.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (PMax) | 🔵 Hipótese (incrementalidade) · 🟢 Confirmado (sobreposição) | Alta | Precisa de aprovação | Performance |

**Referência Google** — [Novidades em campanhas Performance Max (experimentos)](https://support.google.com/google-ads/answer/13311048)

**Evidência interna** — Auditoria WM | Comprar (PMax), tópicos 1 e 2

---

#### EST-02 · Asset group fraco absorvendo o aumento de orçamento

**Situação** — Depois de um aumento de verba na PMax, um asset group específico recebe a maior parte do incremento enquanto a taxa de conversão dele cai.

**Diagnóstico** — Na PMax Principal do Comprar, o asset group "30 Anos - Público CDP" já vinha com a taxa de conversão caindo (0,15% para 0,04% entre 12 e 18/09). Após o aporte, as impressões dele subiram 159% e o custo 50,55%, contra 17,11% do asset group "Conversão A".

**Como verificar** — PMax → Grupos de recursos, comparando custo, conversões e taxa de conversão antes e depois de cada mudança de orçamento.

**Recomendação** — Ler a performance por asset group sempre que houver alteração de orçamento em PMax. Avaliar pausa ou reformulação do asset group com desempenho persistentemente inferior.

**Guardrail** — Pausar asset group também muda o aprendizado da campanha. Aplicar em janela própria.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (PMax) · rotina em todas as PMax | 🟢 Confirmado | Alta | Executa e comunica | Performance |

**Referência Google** — [Novidades em campanhas Performance Max (relatórios por grupo de recursos)](https://support.google.com/google-ads/answer/13311048)

**Evidência interna** — Matriz de Risco — Aumento de CPA, fator Extra (asset group PMax)

---

#### EST-03 · Asset groups separados só por sinal de audiência

**Situação** — Asset groups com nomes e sinais de audiência diferentes, mas temas de pesquisa, textos, imagens e URLs praticamente iguais.

**Diagnóstico** — Em PMax, sinal de audiência não é segmentação rígida. Se criativo, tema e destino são iguais, os grupos não criam universos distintos. Em Vender, os três grupos ativos (`anuncie_seu_carro_online`, `anuncie_seu_carro_hoje`, `anuncie_e_troque_de_carro`) usam temas quase idênticos. Em Santander, grupos de remarketing e base de contratos têm CTR maior, mas CPA pior e menor retorno por valor.

**Como verificar** — Abrir cada asset group e comparar temas de pesquisa, assets e URL final.

**Recomendação** — Estruturar asset groups por proposta de valor ou intenção, com criativos e destinos coerentes. Exemplos para Vender: venda rápida, segurança e confiança, melhor preço, vender para trocar, remarketing de quem iniciou o fluxo. Simplificar grupos que existem apenas para separar público.

**Guardrail** — Mudança estrutural com impacto no aprendizado. Planejar e aplicar em janela própria.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (PMax) · Santander (PMax) | 🟢 Confirmado | Média | Precisa de aprovação | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria WM | Vender (PMax), tópico 5 · Auditoria Santander Financiamentos (PMax), tópico 6

---

#### EST-04 · Taxonomia de grupos que não se reflete na entrega

**Situação** — Grupos com papéis nominais diferentes (por exemplo, "Carro" e "Marcas") recebem as mesmas consultas.

**Diagnóstico** — Em Santander, o grupo Marcas captura muitas consultas genéricas e o grupo Carro recebe buscas com marcas de veículos e de bancos. O grupo Marcas não tem lista de inclusão de marcas configurada. Com ampla e AI Max, o algoritmo cruza as intenções.

**Como verificar** — Termos de pesquisa segmentados por grupo de anúncios.

**Recomendação** — Decidir se Carro e Marcas devem ter papéis distintos. Se sim, impor a separação com negativas cruzadas e inclusões. Se não, simplificar e organizar por intenção ou fase de decisão.

**Guardrail** — Tratar dentro do desenho de estrutura ideal.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Santander (Search) | 🟢 Confirmado | Média | Precisa de aprovação | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria Santander Financiamentos (Search), tópico 3

---

#### EST-05 · A mesma intenção sendo paga em mais de uma conta

**Situação** — Termos de financiamento aparecem com investimento relevante nas contas Comprar e Expansão, além da conta Santander.

**Diagnóstico** — Entre junho e agosto, Comprar e Expansão investiram juntas R$ 251,2 mil em termos de financiamento, mais que o investimento total da Search de Santander no mesmo período (R$ 205,9 mil). A maior parte vem de correspondência ampla incidental, DSA e palavras-chave soltas, sem governança dedicada. A Expansão chegou a operar uma campanha dedicada de financiamento, hoje pausada sem racional documentado.

**Como verificar** — Termos de pesquisa das três contas filtrados por "financ", com a origem da correspondência.

**Recomendação** — Criar leitura consolidada de intenção de financiamento entre as três contas. Levar ao negócio a pergunta: faz sentido aproximar a gestão de Santander da gestão de Comprar e Expansão?

**Guardrail** — Não é recomendação de execução imediata. É decisão de gestão, não de campanha.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Santander · Comprar · Expansão | 🟡 Em avaliação | Média | Precisa de aprovação | Negócio Webmotors |

**Referência Google** — Não se aplica.

**Evidência interna** — Auditoria Santander Financiamentos (Search), tópico 11

---

#### EST-06 · PMax sem feed de produtos onde o feed pode agregar

**Situação** — Campanhas PMax, Demand Gen ou Vídeo com o campo de feed de produtos "Não configurado".

**Diagnóstico** — O Comprar já tem Merchant Center vinculado, mas roda duas PMax similares sem estrutura com feed. A Expansão não tem feed. Demand Gen e Vídeo do Feirão também estavam sem feed. Para Vender, o feed não tem relevância crítica.

**Como verificar** — Configurações da campanha → Feed de produtos. Ferramentas → Contas vinculadas → Merchant Center.

**Recomendação** — Testar uma PMax com feed vinculado, medindo o valor real do feed contra a PMax padrão (backlog T-03). Na Expansão, confirmar primeiro qual conta de Merchant Center usar e estruturar o feed com estoque das regiões.

**Guardrail** — Tratar como teste, não como migração.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar · Expansão | 🟡 Em avaliação | Média | Precisa de aprovação | Performance + Negócio Webmotors |

**Referência Google** — Não mapeada.

**Evidência interna** — Auditoria Feed - Merchant Center (PMax) · página 11 — Recomendações e Quick Wins · Auditoria WM | Comprar (Demand Gen), achado DG-11

---

### 4.8 Audiência e experimentos · `AUD`

#### AUD-01 · Teste entre audiências que muda mais de uma variável

**Situação** — Duas campanhas ou dois grupos são comparados como "com CDP" e "sem CDP" (ou "CDP" e "Base de contratos"), e a conclusão é tirada pelo CPA.

**Diagnóstico** — Em Santander (PMax), os testes A e B diferem em orçamento, estratégia de lance (CPA desejado versus Maximizar valor), política de aquisição e mix de canais (A foi 68% Search; B foi 92% YouTube). O sinal da campanha "sem CDP" contém lista de clientes e remarketing. Em Santander (Demand Gen), os grupos CDP e Base de contratos diferem em landing page, faixas etárias elegíveis e escala, com segmentação otimizada ligada. Nenhum dos desenhos permite atribuir o resultado à audiência.

**Como verificar** — Comparar lado a lado todas as configurações dos dois braços do teste.

**Recomendação** — Refazer o experimento mantendo orçamento, lance, geografia, assets, landing page, faixas demográficas, aquisição e temas iguais, e alterando só a audiência. Em Search, usar a ferramenta de experimentos personalizados. Em PMax e Demand Gen, desenhar manualmente com janela e orçamento comparáveis. Confirmar com o time de dados a origem da lista "Cluster - x >= 2137".

**Guardrail** — Só declarar vencedor depois que o mix de canais estabilizar e com leitura por conversão qualificada (SimAprov/ProposalAprov).

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Santander (PMax e Demand Gen) · princípio para qualquer teste | 🟢 Confirmado | Alta | Precisa de aprovação | Performance + Dados / CRM |

**Referência Google** — [Configurar um experimento personalizado](https://support.google.com/google-ads/answer/6261395) · [Sobre a página de experimentos](https://support.google.com/google-ads/answer/10682377)

**Evidência interna** — Auditoria Santander Financiamentos (PMax), tópicos 2, 3, 5 e 8 · Auditoria Santander Financiamentos (Demand Gen), tópicos 1, 2 e 4

---

#### AUD-02 · Nome do grupo não corresponde ao mecanismo real de audiência

**Situação** — Grupos nomeados como reativação de uma base ("anunciantes últimos 6 meses") usam, na prática, segmentos semelhantes com segmentação otimizada ligada.

**Diagnóstico** — Na Demand Gen de Vender, os três grupos por janela de recência usam segmentos semelhantes às listas originais, não as listas em si, e a segmentação otimizada permite expansão além delas. A estrutura funciona como prospecção, não como reativação. Com seed pequeno e expansão aberta, os três grupos tendem a convergir para universos parecidos.

**Como verificar** — Grupo de anúncios → Públicos-alvo: conferir se o segmento é a lista ou um semelhante, e se a segmentação otimizada está ativa.

**Recomendação** — Definir com o negócio se o objetivo é reativação ou prospecção. Se forem os dois, separar: reativação com listas CRM/CDP diretas e expansão controlada; prospecção com semelhantes e segmentação otimizada. Renomear grupos para refletir o mecanismo. Se a expansão eliminar a diferença entre cohorts, consolidar.

**Guardrail** — O Google indica que a segmentação otimizada tende a gerar mais conversões ao mesmo custo em campanhas de conversão. Controlar a expansão faz sentido para medir, não necessariamente para performance.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Demand Gen) · Santander (Demand Gen, mesmo mecanismo) | 🟡 Em avaliação | Alta | Precisa de aprovação | Performance + Negócio Webmotors |

**Referência Google** — [Visão geral de públicos-alvo da Demand Gen](https://support.google.com/google-ads/answer/15594567) · [Práticas recomendadas para campanhas Demand Gen](https://support.google.com/google-ads/answer/14693848)

**Evidência interna** — Auditoria WM | Vender (Demand Gen), tópicos 3 e 4 · Auditoria Santander Financiamentos (Demand Gen), tópico 2

---

#### AUD-03 · Audiência de alta propensão com CPA muito melhor que o restante

**Situação** — Um segmento de dados próprios (por exemplo, Customer AI de alta ou média propensão) aparece com CPA bem abaixo do tráfego não segmentado.

**Diagnóstico** — No Comprar, a audiência Customer AI de alta propensão em `categoria_sp` é 41% mais barata que o resto do tráfego (em observação). Na Demand Gen do Feirão, Customer AI de média propensão em segmentação teve CPA 52% menor que o tráfego não segmentado. No Vídeo, os 18 segmentos de dados próprios tiveram CPA 2,5 vezes melhor que os dois segmentos amplos, que consumiram 79% da verba de audiência.

**Como verificar** — Públicos-alvo → relatório por segmento, com o modo (observação ou segmentação) de cada um.

**Recomendação** — Como ajuste de lance por audiência não é aplicado sob CPA desejado (LANCE-03), a alavanca é estrutural: grupo ou campanha dedicada ao segmento, ou uso como sinal. No Vídeo, separar dados próprios e segmentos amplos em grupos diferentes para medir e controlar a verba.

**Guardrail** — Validar volume da lista antes de isolar. Não concluir sobre segmentos com amostra pequena (por exemplo, marcas com zero conversão em 1 mês de dado).

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (Search, Demand Gen, Vídeo) | 🟡 Em avaliação | Média | Precisa de aprovação | Performance + Dados / CRM |

**Referência Google** — [Sobre o Smart Bidding](https://support.google.com/google-ads/answer/7065882)

**Evidência interna** — Auditoria WM | Comprar (Search), Quick Wins · Auditoria WM | Comprar (Demand Gen), achado DG-09 · Auditoria WM | Comprar (Video), tópico 5

---

#### AUD-04 · Campanha de melhor CPA pausada sem racional documentado

**Situação** — Uma campanha com bom desempenho aparece pausada, e ninguém sabe explicar por quê.

**Diagnóstico** — No Comprar, a `p-max_publico-cdp` teve o melhor CPA da conta (R$ 13,50 a R$ 14,24) e foi pausada em 17/08, gastando cerca de 12 vezes o orçamento cadastrado. Na Expansão, a campanha de financiamento `financiar-teste2` está pausada sem registro de motivo.

**Como verificar** — Histórico de alterações da campanha: data e autor da pausa.

**Recomendação** — Definir o papel da campanha antes de qualquer reativação: se volta, como se diferencia das outras PMax (EST-01) e com qual orçamento. Registrar o motivo de toda pausa (R14).

**Guardrail** — Reativar sem papel definido aumenta a fragmentação entre PMax.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar (PMax Público CDP) · Expansão (`financiar-teste2`) | 🟡 Em avaliação | Baixa | Precisa de aprovação | Performance + Negócio Webmotors |

**Referência Google** — Não se aplica.

**Evidência interna** — Media Snapshot #1, INV-11 · Auditoria WM | Comprar (PMax), tópico 1 · Auditoria Santander Financiamentos (Search), tópico 11

---

### 4.9 Tracking e UTM · `TRK`

#### TRK-01 · URLs de anúncio sem template de tracking

**Situação** — Cliques chegam ao site sem parâmetros UTM e não podem ser atribuídos a campanha ou grupo no Adobe.

**Diagnóstico** — Das URLs mapeadas entre 1/08 e 5/09, 305 páginas acessíveis por clique não têm nenhum parâmetro. O padrão se repete no Comprar e na Expansão, o que indica causa sistêmica ligada à forma como os anúncios de estoque dinâmico são criados: páginas de estoque com filtro de preço, páginas com parâmetro `lkid`, páginas de categoria (/hatches, /sedans), estoque com parâmetro interno `inst` e páginas de financiamento. Em Vender, 7 URLs genéricas de /vender-carro e /vender-moto. Em 191 URLs do Comprar, o template inclui parâmetros extras (`gclsrc` e outro identificador) que não aparecem no restante da campanha.

**Como verificar** — Relatório de URLs de destino (páginas de destino expandidas) e teste do template com o botão "Testar" nas opções de URL.

**Recomendação** — Aplicar o template padrão (seção 9.2) nos anúncios e grupos que levam a esses tipos de página. Validar se os 191 anúncios com parâmetros extras devem manter o template especial ou ser alinhados ao padrão.

**Guardrail** — Alterar template no nível de anúncio reenvia o anúncio para revisão. Preferir os níveis de conta, campanha ou grupo.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar · Expansão · Vender | 🟢 Confirmado | Média | Executa e comunica | Performance (configuração) + Martech (validação no Adobe) |

**Referência Google** — [Sobre o tracking no Google Ads](https://support.google.com/google-ads/answer/6076199)

**Evidência interna** — Diagnóstico de UTMs — Google Ads (período 01/08 a 05/09/2026)

---

#### TRK-02 · Template em mais de um nível gerando utm_campaign divergente

**Situação** — O `utm_campaign` gravado na URL não bate com o nome atual da campanha, ou parte dos anúncios do mesmo grupo sai sem parâmetros.

**Diagnóstico** — Na Demand Gen de Vender, campanha e grupo de anúncios têm templates próprios, e o do grupo acrescenta um sufixo de público ao nome da campanha. Isso explica 6 dos 7 casos de divergência. O Google aplica o template do nível mais específico, então templates em mais de um nível com conteúdos diferentes geram resultados inconsistentes. O mesmo mecanismo explica o caso único em Santander.

**Como verificar** — Opções de URL em cada nível (conta, campanha, grupo, anúncio). Comparar o `utm_campaign` resultante com o nome da campanha.

**Recomendação** — Manter o template em um único nível por campanha (preferencialmente campanha ou conta). Remover o do grupo de anúncios nas Demand Gen de Vender e aplicar a mesma checagem em Santander. Corrigir os 7 casos divergentes.

**Guardrail** — Validar com o Martech a leitura no Adobe depois da mudança.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Demand Gen) · Santander (Demand Gen) | 🟢 Confirmado | Média | Executa e comunica | Performance + Martech |

**Referência Google** — [Sobre o tracking no Google Ads](https://support.google.com/google-ads/answer/6076199)

**Evidência interna** — Diagnóstico de UTMs — Google Ads, seção Demand Gen

---

### 4.10 Higiene de conta e funil · `HIG`

#### HIG-01 · Orçamento cadastrado não descreve a operação

**Situação** — Campanhas gastam bem acima do orçamento diário cadastrado, ou há contas com teto cadastrado muito acima do gasto real.

**Diagnóstico** — No Comprar, a soma dos orçamentos diários das 10 campanhas era R$ 56.100 contra gasto real de R$ 78.625 por dia (140%), com 8 das 10 campanhas acima do próprio orçamento. A coluna de orçamento dos exports repete o valor atual em todas as linhas e não serve como série histórica.

**Como verificar** — Coluna Orçamento versus Custo médio diário por campanha, no mês corrente. Histórico de alterações de orçamento para a série.

**Recomendação** — Manter o cadastro de orçamento coerente com o planejamento real. Para série histórica, usar o histórico de alterações, nunca a coluna do export.

**Guardrail** — Ajustes de cadastro seguem a R3 quando alteram a verba efetiva.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Comprar · Expansão | 🟢 Confirmado | Baixa | Executa e comunica | Performance |

**Referência Google** — Não mapeada.

**Evidência interna** — Media Snapshot #1, INV-08 e INV-12

---

#### HIG-02 · Campanha "Qualificada (com restrições)" por política

**Situação** — Campanha ou asset groups aparecem com status limitado por política.

**Diagnóstico** — Em Santander, a maioria dos asset groups da PMax ativa está limitada por política, com referência à verificação de serviços financeiros. No Brasil, anunciar serviços financeiros (ou segmentar quem busca esses serviços) exige verificação específica. Em Vender, a restrição parece ligada a assets ou grupos históricos.

**Como verificar** — Coluna Status → passar o cursor sobre a restrição. Ferramentas → Gerenciador de políticas.

**Recomendação** — Mapear quais assets ou grupos estão limitados e por qual motivo. Concluir as validações de anunciante e de serviços financeiros antes de escalar orçamento. Remover itens obsoletos que poluem a leitura de status.

**Guardrail** — Limitação por política reduz a escala independentemente de orçamento ou CPA desejado.

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Santander (PMax) · Vender (PMax, higiene) | 🟢 Confirmado | Alta (Santander) · Baixa (Vender) | Executa e comunica | Performance + Negócio Webmotors (verificação) |

**Referência Google** — [Verificação de serviços financeiros](https://support.google.com/adspolicy/answer/13872758)

**Evidência interna** — Auditoria Santander Financiamentos (PMax), tópico 7 · Auditoria WM | Vender (PMax), tópico 10

---

#### HIG-03 · Mobile com CPA materialmente pior que desktop

**Situação** — Mobile concentra a maior parte do investimento, mas o CPA da conversão final é bem maior que o de desktop.

**Diagnóstico** — Em Vender, o CPA mobile é cerca de 27% maior que o de desktop em Search (R$ 174,81 contra R$ 137,32) e cerca de 16% maior em PMax. O gap é consistente entre formatos, o que aponta para o funil pós-clique, não para a mídia.

**Como verificar** — Segmentar → Dispositivo, pela conversão norte. Cruzar com a taxa de avanço por etapa do funil no analytics.

**Recomendação** — Auditar o funil mobile: velocidade, login, formulário, escolha de modalidade, upload, checkout e pagamento. Localizar a etapa de perda antes de qualquer ação de mídia.

**Guardrail** — Não corrigir com ajuste de lance por dispositivo em Smart Bidding (LANCE-03).

| Escopo | Status | Prioridade | Autonomia | Dono |
|---|---|---|---|---|
| Vender (Search e PMax) | 🟢 Confirmado | Média | Precisa de aprovação | Produto / UX |

**Referência Google** — Não se aplica.

**Evidência interna** — Auditoria WM | Vender (Search), tópico 7 · Auditoria WM | Vender (PMax), tópico 7

---

## 5. Visão por conta

Índice dos itens do playbook aplicáveis a cada conta, em ordem de prioridade, e regras específicas que prevalecem sobre a boa prática genérica.

### 5.1 WM | Comprar · 399-829-8994

**Prioridade alta**
LANCE-01 · Congelar alterações e seguir o ritmo de mudanças (alta de CPA de setembro)
LANCE-02 · Rank antes de verba em Search
EST-01 · Sobreposição entre PMax Principal e Supressão
EST-02 · Asset group "30 Anos - Público CDP" absorvendo verba
INT-03 · Marca vazando na PMax
QUAL-01 · Ad Strength e anúncios por grupo (Search e PMax)
CONV-02 · Demand Gen do Feirão em metas padrão da conta (corrigir antes de reativar)
GEO-01 ✅ · GEO-04 ✅ · REDE-01 ✅ · executados em 16/09: manter e monitorar

**Prioridade média**
CONV-01 (revisar as 5 ações do goal PJ) · CONV-04 · CONV-05 · CONV-06 · LANCE-03 · LANCE-04 · LANCE-06 · GEO-03 · REDE-03 · REDE-04 · INT-01 · INT-02 · QUAL-02 · QUAL-03 · EST-06 · AUD-03 · TRK-01

**Prioridade baixa**
REDE-02 · REDE-05 · AUD-04 · HIG-01

**Regras específicas do Comprar**
Parceiros de pesquisa **não** devem ser desligados: entregam share de Proposta acima do Google Search.
Não existe campanha de marca dedicada por decisão deliberada. Não criar uma como correção de vazamento.
Descartar os últimos 4 a 7 dias em qualquer leitura de CPA (atraso de atribuição).
Atribuição comercial: janela de 24 horas por lojista, sem cobrança duplicada.
Setembro tem alta sazonal de CPA a partir do dia 12, observada em 2025 e 2026.

### 5.2 WM | Expansão · 721-883-1035

**Prioridade alta**
CONV-01 · Definir conversão norte (simulação domina o goal)
GEO-01 · Trocar para "Presença" em Search e PMax
GEO-04 · DSA em inglês nas 6 genéricas estaduais
REDE-01 · Desligar Display nas 6 estaduais
INT-02 · Origem de segmentação e universo de URLs da DSA
QUAL-01 · Ad Strength dos asset groups das PMax

**Prioridade média**
CONV-04 · LANCE-02 · LANCE-03 · LANCE-06 · GEO-03 · INT-01 · QUAL-02 · EST-05 · EST-06 · TRK-01

**Prioridade baixa**
REDE-02 · REDE-05 · AUD-04 · HIG-01

**Regras específicas da Expansão**
Não escalar orçamento só porque as campanhas estão limitadas pelo orçamento. Ordem obrigatória: (1) conversão norte, (2) consultas e destinos, (3) CPA desejado, (4) orçamento onde houver ganho comprovado em proposta.
Não desligar AI Max por padrão: medir antes quanto ela amplia consultas e com qual qualidade.
Não cortar YouTube ou Display da PMax só pelo share: abrir composição por canal e por ação antes.

### 5.3 WM | Vender · 966-658-9621

**Prioridade alta**
CONV-03 · Demand Gen com várias metas
CONV-01 · Demand Gen com 13% de Purchase
INT-01 · Termos de compra, modelo e FIPE via AI Max e DSA
INT-02 · Governança de URL (cerca de 5,4 mil exclusões em Search)
INT-04 · Sitelink de moto apontando para /vender-carro
GEO-01 · Trocar para "Presença" em Search e PMax (em janelas separadas)
GEO-04 · DSA em inglês na campanha de Search
QUAL-01 · Um único anúncio concentrando 93% do custo
LANCE-02 · Perda de IS por rank e disputa direta com OLX e Mercado Livre
AUD-02 · Reativação ou prospecção na Demand Gen

**Prioridade média**
LANCE-03 · LANCE-05 · LANCE-06 · GEO-06 · QUAL-02 · EST-03 · TRK-01 · TRK-02 · HIG-03

**Prioridade baixa**
GEO-05 · REDE-02 · REDE-05 · HIG-02

**Regras específicas de Vender**
O sinal de conversão de Search e PMax está correto (Purchase Vender 7D e compras no app fecham o total). O problema principal é governança de intenção e destino, não mensuração.
Nunca comparar o CPA de Vender com o das contas de compra: o evento de conversão é outro.
Anúncios de Vender usam exclusivamente proposta de valor de anunciante. Nenhuma peça reaproveitada de Comprar.
As exclusões de audiência (Anunciantes ativos PF, Perfis orgânicos + CRM, Pjtinhas, BotDetection) são higiene positiva. Manter.
Tablets estão excluídos (-100%) na Demand Gen. Manter enquanto o racional seguir válido.

### 5.4 Webmotors | Santander Financiamentos · 903-694-1523

**Prioridade alta**
GEO-02 · PMax segmentada para todos os países
HIG-02 · Asset groups limitados por política de serviços financeiros
REDE-01 · Display habilitado na campanha de Search
INT-01 · Imobiliário, bancos concorrentes, consórcio e negativado nos termos
AUD-01 · Testes de CDP sem isolamento de variável
CONV-01 · Leitura por SimAprov e ProposalAprov, não por simulação

**Prioridade média**
LANCE-02 · LANCE-03 · LANCE-05 · LANCE-06 · QUAL-03 · EST-03 · EST-04 · EST-05 · AUD-02 · TRK-02

**Prioridade baixa**
GEO-05 · REDE-05

**Regras específicas de Santander**
Escala só com qualidade: interromper aumento de orçamento se o ganho de volume vier com piora de SimAprov ou ProposalAprov.
Não excluir público feminino ou 55+ apenas pelo CPA de simulação. Cruzar antes com as etapas qualificadas.
"Sem CDP" não significa "sem dados próprios": o sinal da PMax ativa contém lista de clientes e remarketing.

---

## 6. Backlog de testes

Itens com status Hipótese ou que dependem de medição controlada. Nenhum teste deve rodar em paralelo com outra mudança na mesma campanha.

| ID | Conta | Hipótese | Desenho | Métrica de sucesso | Risco |
|---|---|---|---|---|---|
| T-01 | Comprar | Parte da conversão atribuída a termos de marca seria capturada pelo orgânico sem mídia paga. | Teste de incrementalidade de marca, isolado de outras mudanças no período. Desenho a estruturar. | Definir antes de iniciar (conversões incrementais totais, pago + orgânico). | Médio |
| T-02 | Comprar | A PMax Supressão não gera conversão incremental relevante sobre a Principal. | Consolidação temporária ou papéis mutuamente exclusivos, com janela estável e sem mudar CPA desejado, orçamento, geografia ou metas. | Conversões totais das PMax e CPA da conta estáveis ou melhores sem a Supressão. | Médio |
| T-03 | Comprar · Expansão | Uma PMax com feed do Merchant Center entrega mais valor que a PMax padrão. | PMax alternativa com feed vinculado, medida contra a PMax padrão. | Definir antes de iniciar (CPA de Proposta e volume). | Baixo a médio |
| T-04 | Comprar | Trocar metas padrão da conta pela meta do Comprar na Demand Gen reduz volume reportado, mas melhora qualidade e comparabilidade. | Nova campanha Demand Gen com meta específica do funil Comprar. | CPA até R$ 30 com volume de pelo menos 50% do volume atual de Proposta. | Baixo a médio |
| T-05 | Comprar | Vídeo é mais eficiente que estático na Demand Gen. | Pausar assets estáticos e rodar só vídeo por 2 semanas. Ler após T-04. | CPA agregado até R$ 5,50 sem queda de volume acima de 10%. | Baixo |
| T-06 | Comprar | Demand Gen de marca em regiões de baixa demanda gera demanda nova sem canibalizar Search. | 2 a 3 regiões de baixa demanda, 4 a 6 semanas, com Search Lift dedicado. | Aumento de pelo menos 5% nas buscas por "webmotors" nas regiões testadas contra controle. | Médio |
| T-07 | Comprar | O CPA menor via app pode ser efeito de estágio de funil, não alavanca real. | Teste controlado de destino (app versus site) em `categoria_sp`. | Definir antes de iniciar (CPA de Proposta por destino). | Médio |
| T-08 | Comprar | Lances diferenciados entre termos genéricos e de modelo melhoram a eficiência em `marcas_sp`. | Separação por intenção dentro da campanha, com alvos próprios. | CPA de Proposta menor sem perda de volume. | Baixo |
| T-09 | Comprar | Vídeo com período maior, TV priorizada e audiências separadas por tipo gera leitura mais robusta. | Campanha de Vídeo com grupos separados (dados próprios e segmentos amplos) e janela maior que 30 dias. | CPV e visualizações completas por grupo; CPL por grupo. | Baixo |
| T-10 | Santander | O CDP melhora a qualidade das simulações. | Refazer o teste variando só a audiência (AUD-01). | CPA de SimAprov e ProposalAprov por braço. | Baixo a médio |
| T-11 | Vender | A janela de recência do anunciante antigo muda a qualidade do Purchase. | Expansão controlada ou restrita por cohort, com relatório separado de seed, semelhante e expansão. | CPA de Purchase por cohort. | Baixo |
| T-12 | Vender · Santander | As campanhas eficientes limitadas pelo orçamento absorvem mais verba sem perder eficiência. | Degraus de 10% a 20% com CPA desejado fixo e gatilho de reversão definido. | CPA da conversão norte dentro da faixa aceitável em cada degrau. | Baixo |

---

## 7. Rotinas operacionais

### 7.1 Diária

Ritmo de gasto por campanha contra o planejado.
Status da estratégia de lance (campanhas em aprendizagem e o motivo).
Diagnóstico das ações de conversão: quedas abruptas de volume ou alertas (CONV-05, LANCE-06).
Campanhas que zeraram entrega sem mudança de status.
Anúncios, assets e grupos reprovados ou limitados por política (QUAL-02, HIG-02).
Registro de toda alteração feita no dia (R14).

### 7.2 Semanal

Termos de pesquisa por cluster de intenção, com atenção a AI Max, DSA e ampla. Novas negativas entram em listas temáticas compartilhadas (INT-01).
Perda de IS por classificação versus orçamento por campanha (LANCE-02).
Composição de conversões por ação: share da conversão norte (CONV-01).
Revisão do histórico de alterações da semana contra a regra de uma alavanca por vez (R1).

### 7.3 Mensal

Distribuição por canal das PMax: custo, CPA e composição (REDE-05).
Relatório de localização: gasto fora da praça (GEO-01, GEO-02).
Informações sobre leilões por conta.
Eficácia dos anúncios e dos asset groups (QUAL-01).
Relatório de páginas de destino e revisão de exclusões de URL (INT-02).
Relatório de placements e revisão das listas de exclusão (REDE-03).
Amostra de URLs finais para checar UTM (TRK-01).
Orçamento cadastrado versus gasto real (HIG-01).
Leitura por asset group das PMax (EST-02).

### 7.4 Antes de cada campanha sazonal (feirões, Black Friday, datas comerciais)

Meta de conversão específica da campanha, nunca metas padrão da conta (CONV-02).
Rede de Display desligada em Search e expansão para Display revisada em Vídeo (REDE-01, REDE-04).
Listas de exclusão de placements aplicadas (REDE-03).
Anúncios completos, sem status "Incompleto".
Opção de local "Presença" e idioma correto (GEO-01, GEO-04).
Pelo menos 2 variações por formato de criativo, com a métrica de avaliação de cada formato definida antes (CPA ou visualização completa para horizontal; engajamento para vertical).
Ajuste de sazonalidade apenas se o evento durar de 1 a 7 dias (LANCE-06).
Reporte da campanha sazonal separado do Always On (R10).

---

## 8. Pendências de validação com o negócio

Decisões que destravam itens em Em avaliação ou Hipótese.

| # | Pergunta | Destrava |
|---|---|---|
| 1 | Qual é a conversão norte de cada conta? Expansão: simulação, proposta ou lead qualificado. Santander: simulação, SimAprov ou ProposalAprov. Vender: Purchase Vender 7D ou Finalização do Anúncio. | CONV-01 · CONV-03 |
| 2 | Comprar: as 5 ações do goal `geral_fluxo-comprar_lead-pj` devem ficar juntas? Há duplicidade de disparo? | CONV-01 |
| 3 | Qual é a função real do `lead_comprar_cdp` e quais critérios o CDP usa para qualificar um lead? | CONV-05 |
| 4 | Existe régua de CRM trabalhando quem simulou e não converteu? (Se sim, a simulação tem valor próprio.) | CONV-01 · REDE-02 |
| 5 | A distribuição da Expansão fora das praças é intencional? Comprar e Expansão devem ter estruturas espelhadas e praças mutuamente exclusivas? | GEO-03 |
| 6 | Existe categoria, marca, praça ou tipo de veículo (0 km ou usado) que o negócio quer priorizar agora? | QUAL-03 · estrutura ideal |
| 7 | Existe regra de negócio que impede simulação de financiamento para certos veículos ou categorias? | Estrutura ideal |
| 8 | Existe público que deve ficar fora das campanhas de financiamento por regra de negócio? | AUD-03 |
| 9 | Santander: moto, consórcio, negativado, refinanciamento e marcas de bancos fazem parte do escopo do produto? | INT-01 |
| 10 | Vender (Demand Gen): o objetivo é reativar antigos anunciantes ou prospectar pessoas parecidas? | AUD-02 |
| 11 | Qual é a função da lista de exclusão "Pjtinhas"? | Higiene de audiência |
| 12 | Qual o critério das exclusões de placement atuais em nível de conta (por exemplo, Jovem Pan)? | REDE-03 |
| 13 | Qual foi o racional das movimentações de verba e de CPA desejado no Comprar em setembro/2026? | LANCE-01 |
| 14 | Vender: quando e por que a campanha de Search passou a otimizar para Purchase Vender 7D em vez de Finalização do Anúncio? | CONV-03 |
| 15 | Santander: a lista "Cluster - x >= 2137" é alimentada pelo CDP? | AUD-01 |
| 16 | Faz sentido aproximar a gestão de Santander da gestão de Comprar e Expansão? | EST-05 |
| 17 | Qual conta de Merchant Center deve ser vinculada à Expansão? | EST-06 |
| 18 | Os segmentos in-market sugeridos no Vídeo (SUVs, Trucks, Luxury, Motor Vehicles) estavam ativos? Há plano de Vídeo para Black Friday e dezembro? | AUD-03 · T-09 |

---

## 9. Glossário e padrões

### 9.1 Glossário

| Termo | Significado nesta operação |
|---|---|
| **Proposta** | `Lead_PJ_Carro_FormPropostas` + envio de proposta pelo app (`adj_enviopropostatotalpj_android` e `_ios`). Evento de negócio do funil Comprar. |
| **Financiamento (formulário)** | `Lead_PJ_Carro_FormFinanciamento`. |
| **Agendamento** | `Lead_PJ_Carro_AgendamentoVideoChamada`. Ação de contato mais profunda, volume residual (cerca de 0,3%). |
| **Simulação** | `simulações` (web) + `adj_simulacaofinanciamento_android` e `_ios`. Etapa intermediária; exige dados do usuário. |
| **SimAprov / ProposalAprov** | `Purchase_SimAprov` e `Purchase_ProposalAprov`. Etapas qualificadas do funil de financiamento. |
| **CDP (lead)** | `lead_comprar_cdp`. Ação importada via correspondência de cliques; função como métrica de qualidade em validação. |
| **Purchase Vender 7D** | `[MCC] Purchase - Vender 7D` + compras no app (`adj_purchase_vender_android` e `_ios`). Conversão de Search e PMax de Vender. |
| **Finalização do Anúncio** | `[MCC] Finalização do Anúncio - Vender`. Usada nas campanhas de Vender pausadas. |
| **Modalidade / Checkout** | `Fluxo_Vender_Modalidade` e `Fluxo_Vender_CheckOut`. Etapas intermediárias do funil Vender. |
| **Goal PJ do Comprar** | `geral_fluxo-comprar_lead-pj` (ID 6450803547). Meta personalizada usada em Search, PMax e Vídeo do Comprar. |
| **Goal da Expansão** | "MCC - Expansão - Lead PJ (Site e App)". |
| **Metas padrão da conta** | Modo em que a campanha usa todas as metas marcadas como padrão da conta, sem filtro por produto. |
| **IS perdida (classificação / orçamento)** | Percentual de impressões perdidas por Ad Rank insuficiente ou por falta de orçamento. |
| **AI Max** | Conjunto de recursos de Search que inclui correspondência de termos de pesquisa, personalização de texto e expansão de URL final. |
| **Expansão de URL final** | Permite ao Google trocar a URL final por outra página do domínio. Com ela ligada, feed de páginas orienta, mas não restringe. |
| **Segmentação otimizada** | Na Demand Gen, permite entrega além dos públicos selecionados. |
| **Always On** | Campanhas permanentes, lidas separadamente das sazonais. |

### 9.2 Padrão oficial de UTM

Estrutura encontrada nas URLs com tracking correto (acima de 99,7% em Comprar, Vender e Expansão):

```
utm_id={campaignid}&utm_source=google&utm_medium={search|demand-gen}&utm_campaign={nome da campanha}&utm_content={adgroupid}&utm_term={creative|targetid}&idcmp={código interno}
```

Variações esperadas: `utm_medium` assume "search" em pesquisa, "demand-gen" em Demand Gen e "retargeting" em App. Campanhas de instalação de app usam a convenção `google:install:...` e a atribuição própria da Play Store, por isso a ausência de UTM nelas é esperada. O valor de `utm_campaign` deve corresponder exatamente ao nome da campanha no Google Ads.

---

## 10. Fontes

### 10.1 Auditorias e estudos que sustentam o playbook

| Documento | Conta | Corte / atualização |
|---|---|---|
| Auditoria de conta — WM \| Comprar (Search) | Comprar | 01/01–31/08/2026 · atualizado 25/09 |
| Auditoria de conta — WM \| Comprar (PMax) | Comprar | 01/01–31/08/2026 · v2 de 25/09 |
| Auditoria de conta — WM \| Comprar (Demand Gen) | Comprar | julho/2026 · v3 de 17/09 |
| Auditoria de conta — WM \| Comprar (Video) | Comprar | julho/2026 · 17/09 |
| Matriz de Risco — Aumento de CPA (WM \| Comprar) | Comprar | evidência até 21/09/2026 |
| Auditoria de conta — WM \| Expansão (Search) | Expansão | 01/01–31/08/2026 · 13/09 |
| Auditoria de conta — WM \| Expansão (PMax) | Expansão | 01/01–31/08/2026 · 25/09 |
| Auditoria de conta — WM \| Vender (Search) | Vender | 01/01–31/08/2026 · 25/09 |
| Auditoria de conta — WM \| Vender (Performance Max) | Vender | 01/01–31/08/2026 · 25/09 |
| Auditoria de conta — WM \| Vender (Demand Gen) | Vender | desde 17/06/2026 · 25/09 |
| Auditoria de conta — Santander Financiamentos (Search) | Santander | 01/01–31/08/2026 · 25/09 |
| Auditoria de conta — Santander Financiamentos (Performance Max) | Santander | 25/09 |
| Auditoria de conta — Santander Financiamentos (Demand Gen) | Santander | 25/09 |
| Media Snapshot #1 — Webmotors, o ano até aqui | MCC | 01/01–30/08/2026 |
| Diagnóstico de UTMs — Google Ads | Todas | 01/08–05/09/2026 |
| Feed - Merchant Center (PMax) | Comprar · Expansão | setembro/2026 |
| Estrutura de Mídia Ideal — Cluster por Conta | Todas | em andamento · 24/09 |
| 11 — Recomendações e Quick Wins | Comprar · Expansão | v1.6 de 11/09 |

### 10.2 Referências oficiais do Google Ads Help

| Tema | Artigo |
|---|---|
| Ações de conversão principais e secundárias | https://support.google.com/google-ads/answer/11461796 |
| Metas de conversão específicas da campanha | https://support.google.com/google-ads/answer/9143218 |
| Metas de conversão padrão da conta | https://support.google.com/google-ads/answer/4677036 |
| Atualizar metas de conversão | https://support.google.com/google-ads/answer/13810904 |
| Valores de conversão | https://support.google.com/google-ads/answer/13064207 |
| Duração do período de aprendizado | https://support.google.com/google-ads/answer/13020501 |
| Sobre o Smart Bidding | https://support.google.com/google-ads/answer/7065882 |
| Ajustes de sazonalidade | https://support.google.com/google-ads/answer/10369906 |
| Ajustes de sazonalidade e exclusões de dados em PMax | https://support.google.com/google-ads/answer/12351101 |
| Dados de parcela de impressões | https://support.google.com/google-ads/answer/7103314 |
| Segmentação por locais geográficos | https://support.google.com/google-ads/answer/2453995 |
| Domínio e idioma em anúncios dinâmicos de pesquisa | https://support.google.com/sa360/answer/9797935 |
| Expansão para Display em campanhas de pesquisa | https://support.google.com/google-ads/answer/7193800 |
| Excluir páginas da web e vídeos | https://support.google.com/google-ads/answer/2454012 |
| Adequação da marca na Performance Max | https://support.google.com/google-ads/answer/13607727 |
| AI Max para campanhas de pesquisa | https://support.google.com/google-ads/answer/15910187 |
| Listas de palavras-chave negativas | https://support.google.com/google-ads/answer/7449003 |
| Feeds de páginas na Performance Max | https://support.google.com/google-ads/answer/13568488 |
| Expansão de URL final na Performance Max | https://support.google.com/google-ads/answer/14337539 |
| Controles de URL na Performance Max | https://support.google.com/google-ads/answer/16672777 |
| Exclusões de marca | https://support.google.com/google-ads/answer/16669487 |
| Aplicar exclusões de marca | https://support.google.com/google-ads/answer/14505308 |
| Eficácia do anúncio (RSA) | https://support.google.com/google-ads/answer/9921843 |
| Novidades em Performance Max | https://support.google.com/google-ads/answer/13311048 |
| Públicos-alvo da Demand Gen | https://support.google.com/google-ads/answer/15594567 |
| Práticas recomendadas para Demand Gen | https://support.google.com/google-ads/answer/14693848 |
| Experimentos personalizados | https://support.google.com/google-ads/answer/6261395 |
| Página de experimentos | https://support.google.com/google-ads/answer/10682377 |
| Tracking no Google Ads | https://support.google.com/google-ads/answer/6076199 |
| Verificação de serviços financeiros | https://support.google.com/adspolicy/answer/13872758 |

---

## 11. Controle de versão

| Versão | Data | Alteração |
|---|---|---|
| v1.0 | 26/09/2026 | Primeira versão consolidada a partir das auditorias das quatro contas primárias. 45 itens em 10 categorias, 12 testes em backlog e 18 pendências de validação. |

**Como manter este playbook vivo:** todo item muda de status quando a evidência muda. Ao executar um item, atualizar o status para Executado com a data. Ao concluir um teste do backlog, promover o resultado a item Confirmado ou descartar a hipótese. Revisar o documento inteiro a cada ciclo mensal.

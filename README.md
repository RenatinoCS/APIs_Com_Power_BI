# Análise de Resultados de Campanhas Multicanal via APIs

## Introdução

Este projeto foi desenvolvido pela equipe 'Brain Tech' como projeto final da Soulcode. O objetivo principal foi explorar a conexão com APIs de diferentes plataformas de publicidade online para coletar e analisar dados de campanhas. Através da integração dessas APIs com o Power BI, buscamos obter insights valiosos sobre o desempenho de campanhas em diferentes canais: TikTok Ads, Meta Ads (Facebook e Instagram) e Google Ads.

A análise envolveu o estudo das documentações de cada API para identificar os melhores métodos de conexão e os endpoints que fornecem acesso aos principais indicadores de desempenho (KPIs).

## As APIs Estudadas

### TikTok Ads API

A TikTok Ads API (ou TikTok Marketing API) permite a integração de sistemas com a plataforma de anúncios do TikTok para automatizar a criação e gerenciamento de campanhas, extração de dados de desempenho (relatórios), consulta a contas, criativos e públicos, e acompanhamento de eventos.

**Formatos de Mídia:** In-Feed Ads, TopView Ads, Brand Takeover, Branded Hashtag Challenge, Branded Effects e Spark Ads.

**KPIs:** Impressões, Cliques, CTR, CPC, CPM, CPA, Conversões, ROAS, Gasto Total e Ticket Médio.

**Investigação Técnica:** Documentação oficial da TikTok for Developers. Endpoints relevantes: `/open_api/v1.2/report/ad/get/`, `/open_api/v1.2/ad/create/`, `/open_api/v1.2/campaign/get/`, `/open_api/v1.2/adgroup/get/`, `/open_api/v1.2/pixel/conversion/list/`, `/open_api/v1.2/budget/update/`. Autenticação via OAuth 2.0. Limitações: rate limits e dados históricos (até 180 dias).

### Meta Ads API

A Meta Ads API (anteriormente Facebook Marketing API) possibilita a integração com o gerenciador de anúncios do Facebook e Instagram para automatizar a criação e gerenciamento de campanhas, extração de dados de desempenho em tempo real, gerenciamento de criativos, públicos e orçamentos, e acompanhamento de eventos via Pixel ou API de Conversões.

**Formatos de Mídia:** Imagem, Vídeo, Carrossel, Coleção, Reels Ads, Stories Ads, Slideshow, Instant Experience e anúncios de Mensagens/WhatsApp.

**KPIs:** Impressões, Cliques, CTR, CPC, CPM, CPA, Conversões, ROAS e Valor Gasto.

**Investigação Técnica:** Documentação da Meta for Developers – Marketing API (v19.0+). Endpoints relevantes: `/act_{ad_account_id}/campaigns`, `/act_{ad_account_id}/adsets`, `/act_{ad_account_id}/ads`, `/act_{ad_account_id}/insights`, `/adcreatives`, `/customaudiences`, `/events`. Autenticação via OAuth 2.0. Limitações: rate limit e dados históricos (até 37 meses para insights).

### Google Ads API

A Google Ads API permite a integração com a plataforma de anúncios do Google para automatizar a criação e gerenciamento de campanhas, grupos de anúncios e anúncios, extração de dados de desempenho detalhados, consulta a diversos recursos e otimização de orçamentos e lances.

**Formatos de Mídia:** Rede de Pesquisa, Rede de Display, YouTube (Campanhas de Vídeo), Shopping, Campanhas para Apps e Performance Max.

**KPIs:** Impressões, Cliques, CTR, CPC, CPM, Conversões, CPA, Gasto Total, ROAS e Receita.

**Investigação Técnica:** Documentação oficial da Google Ads API e GAQL. Endpoints/Consultas relevantes: `/v16/customers/{customerId}/googleAds:search`, `/v16/customers/{customerId}/campaigns:create`, `/v16/customers/{customerId}/biddingStrategies:mutate`, `/v16/customers/{customerId}/conversionActions:search`. Autenticação via OAuth 2.0. Limitações: rate limit e linhas por consulta GAQL.

## Conexão com o Power BI

A equipe optou por utilizar o Power BI como ferramenta de visualização e análise dos dados coletados via APIs. Através de conectores web e a capacidade do Power BI de trabalhar com fontes de dados JSON (formato comum das respostas das APIs REST), buscamos integrar os dados das diferentes plataformas em um único modelo de dados. Isso permitiu a criação de dashboards comparativos e a identificação de insights sobre o desempenho das campanhas nos diferentes canais.

[Aqui você pode adicionar detalhes específicos sobre como a conexão foi feita no Power BI, como a utilização de consultas M ou conectores específicos, se houve algum desafio técnico na integração, e por que o Power BI foi considerado a melhor ferramenta para esta análise.]

## Endpoints e KPIs

Identificamos os endpoints mais relevantes de cada API para acessar os principais KPIs, possibilitando a extração de insights sobre o desempenho das campanhas. Os KPIs chave que buscamos analisar incluíram:

* Impressões: Para avaliar o alcance das campanhas.
* Cliques: Para medir o interesse e engajamento inicial.
* CTR (Click-Through Rate): Para avaliar a relevância dos anúncios.
* CPC (Cost Per Click): Para entender a eficiência do custo por clique.
* CPM (Cost Per Mille): Para avaliar o custo por mil impressões.
* CPA (Cost Per Acquisition/Conversion): Para medir o custo por resultado.
* Conversões: Para quantificar as ações desejadas.
* ROAS (Return on Ad Spend): Para avaliar o retorno financeiro das campanhas.
* Gasto Total: Para monitorar o investimento.
* Ticket Médio (para TikTok Ads): Relevante para campanhas de e-commerce.
* Receita (para Google Ads): Para análise de retorno sobre o investimento.

## Simulação de Campanhas

Para demonstrar o potencial da análise sem comprometer dados de empresas parceiras, simulamos o desempenho de três campanhas hipotéticas:

* **Academia de dados:** Apresentando um curso de Análise de Dados com foco em mídia digital.
* **TurboShot CODE ENERGY:** Energético para desenvolvedores e entusiastas de tecnologia.
* **Banco Solari CONTA CORRENTE GRÁTIS:** Conta corrente gratuita para pessoas com renda até R$ 8.000/mês.

Essas simulações permitiram realizar análises comparativas de desempenho entre as plataformas, considerando métricas como alcance, engajamento e custo por resultado, alinhadas com as características de cada plataforma e os objetivos de cada campanha simulada.

## Análise Comparativa

Através da integração dos dados no Power BI, realizamos uma análise comparativa do desempenho das campanhas simuladas nas três plataformas: TikTok Ads, Meta Ads (Facebook e Instagram) e Google Ads.

**Visão Geral:**

* **ROAS por Empresa e Plataforma:** O Banco Solari demonstrou otimização eficaz em Google e Facebook, mas pode ajustar a estratégia no TikTok. A TurboShot apresentou um bom desempenho no TikTok, sugerindo potencial para maior investimento. A Academia de Dados precisa reavaliar suas estratégias, especialmente no Instagram.
* **Gasto Total e Receita Estimada por Plataforma:** Todas as plataformas geraram receita superior ao gasto, indicando um ROAS positivo geral. O Google liderou em receita estimada, seguido por Facebook e Instagram. O TikTok, com menor gasto, também apresentou retorno positivo, sinalizando potencial de crescimento.

**Insights Específicos por Plataforma:**

* **TikTok Ads:** A TurboShot obteve um ROAS significativamente alto. O Banco Solari apresentou boa performance de engajamento e conversão. A Academia de Dados pode precisar de ajustes na segmentação ou criativos.
* **Meta Ads - Instagram:** O Banco Solari destacou-se com alto ROAS. A TurboShot também mostrou eficiência. A Academia de Dados teve um retorno menor, indicando necessidade de revisão.
* **Meta Ads - Facebook:** A TurboShot, a Academia de Dados e o Banco Solari apresentaram ROAS positivos, com o Banco Solari liderando em impacto e escala.
* **Google Ads:** Todas as empresas (Academia de Dados, Banco Solari e TurboShot) demonstraram um ROAS elevado, indicando campanhas eficientes.

Em geral, Google e Facebook se mostraram plataformas com desempenho consistente. O TikTok surpreendeu positivamente para a TurboShot, enquanto o Instagram apresentou oportunidades de melhoria, especialmente para a Academia de Dados.

## Próximos Passos

Com base nesta análise inicial, os próximos passos para otimizar as campanhas poderiam incluir:

* **Banco Solari:** Explorar o aumento do investimento no TikTok, mantendo a performance sólida em Google e Facebook.
* **TurboShot:** Analisar os criativos e segmentações bem-sucedidos no TikTok e Facebook para aplicar em outras plataformas, buscando melhorar a taxa de conversão no TikTok.
* **Academia de Dados:** Revisitar a estratégia no Instagram, focando em otimizações de criativos, segmentação e a jornada pós-clique. Investigar o sucesso do ROAS no Google Ads para replicar aprendizados em outras plataformas.
* **Geral:** Considerar o Google e o Facebook como plataformas prioritárias para escala, dada a sua performance consistente e alto retorno. Explorar o potencial de crescimento do TikTok com testes de maior investimento.

Além disso, poderíamos refinar o dashboard no Power BI para apresentar esses insights de forma mais visual e interativa, facilitando o acompanhamento contínuo do desempenho das campanhas.

## Equipe 'Brain Tech'

* Cristiane Meira
* Layla fé
* Maria Eduarda
* Mariana Araújo
* Myriam Nascimento
* Raissah Laborda
* Viviane Santos 
* Renato Costa


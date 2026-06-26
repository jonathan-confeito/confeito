# Loja Confeitô V1 — Especificação Produto/Técnica

## 1. Visão

A Loja Confeitô V1 é a evolução natural do Confeitô de um app interno de gestão para um sistema simples de venda.

O Confeitô continua sendo a área privada da confeiteira para cadastrar insumos, montar receitas, calcular preços, acompanhar estoque, registrar vendas e entender o negócio. A Loja Confeitô passa a ser a vitrine pública: um link bonito, simples e profissional para clientes escolherem produtos e enviarem pedidos pelo WhatsApp.

A proposta da V1 é ser premium e elegante, mas sem complicar. O cliente final precisa entender rapidamente onde está, o que pode comprar, quanto custa e como finalizar. A confeiteira precisa conseguir publicar produtos sem virar uma operadora de e-commerce.

Resumo do posicionamento:

> Confeitô Loja: sua loja online de doces, pronta para receber pedidos pelo WhatsApp.

## 2. O que a loja resolve

Hoje o Confeitô ajuda a confeiteira a saber quanto custa produzir, qual preço cobrar, quanto vendeu e quanto lucrou. A Loja Confeitô adiciona a próxima etapa: publicar e vender.

Ela resolve estes pontos:

- A confeiteira ja calculou o preco no Confeito, mas ainda precisa mandar cardapio manualmente.
- O cliente final quer ver produtos, fotos, precos e formas de compra sem ficar pedindo tudo por mensagem.
- O pedido precisa chegar organizado no WhatsApp da confeiteira.
- A confeiteira precisa de uma vitrine profissional sem depender de planilha, PDF, link improvisado ou marketplace poluido.
- O Confeito passa a ter mais valor percebido: gestao, precificacao, estoque, negocio e venda em um fluxo simples.

## 3. Princípios de UX

A loja deve seguir estes principios:

- Premium e elegante, com visual limpo.
- Simples antes de completa.
- Nao confundir a cliente final.
- A pessoa deve entender em 5 segundos que esta em uma loja de doces e como pedir.
- O preco precisa estar sempre claro.
- O botao principal precisa ser evidente.
- O fluxo deve ser curto: ver produto, adicionar, identificar, enviar no WhatsApp.
- Sem excesso de banners.
- Sem parecer marketplace generico ou poluido.
- Sem checkout pesado na V1.
- Sem pagamento online na V1.
- Sem exigir conta para cliente final.
- Sem expor dados internos da confeiteira.

### Direção visual

A Loja Confeitô deve parecer uma boutique digital de doces/confeitaria artesanal.

Direção recomendada:

- Visual premium, limpo e caloroso.
- Fundo claro/quente, como creme ou off-white.
- Cores principais próximas da identidade atual: marrom, caramelo e tons suaves.
- Rosa/champagne pode entrar apenas como apoio, se fizer sentido.
- Fotos dos produtos devem ser valorizadas.
- Cards com bastante respiro.
- Botões grandes e óbvios.
- Poucos textos por tela.
- Preço sempre visível.
- Evitar excesso de banners e elementos competindo pela atenção.
- Não copiar visualmente Anota Aí ou iFood; usar apenas como referência de fluxo.
- Regra de ouro: bonito o suficiente para parecer profissional, simples o suficiente para qualquer cliente comprar sem pensar.

## 4. Navegação interna do Confeitô

Proposta futura para a barra inferior do app privado:

- Insumos
- Receitas
- Precos
- Negocio
- Loja

A aba Ajustes pode migrar futuramente para um menu lateral ou menu hamburguer. Essa mudanca nao deve ser feita junto da primeira implementacao da Loja, porque mexe em navegacao central do app e aumenta o risco para usuarios reais.

Recomendacao:

1. Manter a navegacao atual ate a arquitetura da Loja estar definida.
2. Criar a aba Loja somente quando houver uma experiencia interna minima e segura.
3. Migrar Ajustes para menu secundario em patch separado, depois de validar que a Loja justifica ocupar a quinta aba.

## 5. Área Loja para a confeiteira

A area Loja dentro do Confeito deve ser a central de publicacao e configuracao.

Telas propostas:

- Minha loja: resumo do status, link publico, produtos publicados e atalhos.
- Perfil da loja: nome publico, logo, capa, descricao, WhatsApp, cidade, bairro, horario e status.
- Produtos da loja: selecao de receitas/produtos internos que aparecem na loja publica.
- Categorias: organizacao simples, como Bolos, Docinhos, Fatias, Kits, Sobremesas.
- Link da loja: slug, botao copiar link, preview e orientacao para compartilhar.
- Pedidos pelo WhatsApp: configuracao da mensagem gerada e instrucoes de atendimento.
- Indique e ganhe: area futura para programa de indicacao.

Na V1, a tela Minha loja pode concentrar quase tudo, desde que continue clara. Telas separadas podem entrar quando houver mais configuracoes.

## 6. Dados da loja

Campos provaveis para a loja:

- ativa: booleano para publicar ou pausar a loja.
- slug: identificador publico do link.
- nomeLoja: nome publico da loja.
- logo: imagem publica da marca.
- capa: imagem de topo ou banner simples.
- descricaoCurta: texto curto de apresentacao.
- whatsapp: numero publico para receber pedidos.
- cidade: cidade atendida.
- bairro: bairro/base de retirada, se aplicavel.
- horarioTexto: horario exibido de forma simples.
- statusManual: aberta, fechada ou sob encomenda.
- pedidoMinimo: valor minimo opcional.
- retiradaAtiva: permite retirada.
- entregaAtiva: permite entrega.
- taxaEntrega: valor opcional, quando a entrega for simples.
- formasPagamento: Pix, dinheiro, cartao, combinacao no atendimento.
- mensagemAutomaticaPedido: texto base para WhatsApp.

Observacao importante: esses campos nao existem hoje no payload atual. Eles devem ser planejados antes de qualquer implementacao real.

## 7. Produtos da loja

Campos provaveis para cada produto publicado:

- produto_id: referencia ao produto/receita interna.
- visivelNaLoja: booleano.
- nomePublico: nome exibido ao cliente.
- descricaoPublica: texto comercial simples.
- fotoPublica: imagem segura para a vitrine.
- categoria: categoria publica.
- preco: preco exibido na loja.
- disponivel: produto pode ser pedido agora.
- destaque: aparece em secao de destaque.
- ordem: ordenacao manual.
- permiteObservacao: cliente pode escrever observacao.
- adicionais: futuro, para recheios, tamanhos, coberturas ou extras.
- opcoes: futuro, para variacoes como tamanho P/M/G.

O produto interno do Confeito contem dados sensiveis para a loja publica, como itens da receita, custos, rendimento e calculos. A loja deve publicar somente uma projecao segura do produto.

## 8. Loja publica do cliente

Telas e estados da loja publica:

- Home da loja: marca Confeito no topo, nome da loja, logo/foto, status, descricao curta e CTA.
- Categorias: navegacao simples por tipo de produto.
- Lista de produtos: foto, nome, descricao curta, preco e disponibilidade.
- Produto aberto: foto maior, descricao, preco, quantidade, observacoes e botao adicionar.
- Adicionais/opcionais: nao obrigatorio na primeira V1, mas a estrutura deve prever futuro.
- Observacoes: campo simples por item.
- Carrinho: itens, quantidades, subtotal, retirada/entrega e pagamento.
- Identificacao: nome e WhatsApp do cliente.
- Finalizacao: revisao do pedido e botao para enviar no WhatsApp.
- Envio para WhatsApp: abrir conversa com mensagem pronta para a confeiteira.

O fluxo deve evitar qualquer coisa que pareca pagamento online ou pedido confirmado automaticamente. Na V1, o WhatsApp ainda e a confirmacao operacional.

## 9. Carrinho e checkout V1

Definicao recomendada para V1:

- Sem pagamento online.
- Sem conta para cliente final.
- Carrinho local no navegador.
- Cliente informa nome.
- Cliente informa WhatsApp.
- Cliente escolhe retirada ou entrega.
- Cliente escolhe forma de pagamento preferida.
- Cliente pode escrever observacoes gerais.
- Cliente pode escrever observacao por produto.
- Sistema monta uma mensagem organizada.
- Sistema abre o WhatsApp da confeiteira.

O carrinho pode ser armazenado apenas em memoria ou localStorage do navegador publico. Nao e necessario salvar pedido no Supabase na primeira versao se a estrategia for reduzir risco.

Mesmo sem salvar dados do cliente na V1, o cliente informara nome e WhatsApp para montar o pedido. A tela deve usar microcopy simples:

> Usaremos seus dados apenas para enviar este pedido à loja pelo WhatsApp.

Se no futuro os pedidos forem salvos, sera necessario revisar politica de privacidade, retencao e consentimento. A loja deve evitar coletar dados desnecessarios. Endereco completo so deve ser pedido se entrega estiver ativa e se for necessario para concluir o pedido.

## 10. Mensagem do pedido para WhatsApp

Exemplo de mensagem:

```text
Olá! Quero fazer este pedido 😊

Loja: [NOME DA LOJA]
Cliente: [NOME]
WhatsApp: [WHATSAPP]

Pedido:
- 1x [Produto] — R$ XX,XX
  Obs.: [observação]

Subtotal: R$ XX,XX
Entrega/Retirada: [tipo]
Quando: [agora/agendado]
Pagamento: [forma]

Observações gerais: [texto]
```

A mensagem nao deve incluir:

- custo;
- lucro;
- margem;
- taxa;
- imposto;
- itens internos da receita;
- rendimento;
- estoque interno, salvo uma disponibilidade publica simples.

### Abertura do WhatsApp na loja publica

Diferente da tela interna Precos, onde a acao e apenas copiar mensagem, na Loja publica e aceitavel abrir WhatsApp.

Na Loja V1, o botao final pode abrir `wa.me` ou link equivalente com mensagem preenchida. Isso deve acontecer somente depois que o cliente revisar o pedido e tocar em uma acao explicita, como:

> Enviar pedido no WhatsApp

O numero usado deve ser o WhatsApp publico configurado pela confeiteira. O texto do pedido deve ser montado sem expor dados internos. Nao usar WhatsApp API oficial na V1. Nao enviar automaticamente sem acao do cliente.

## 11. Rotas e links públicos

Opcoes avaliadas:

### Opcao A - `useconfeito.com/loja/[slug]`

Vantagens:

- Marca principal concentrada no mesmo dominio.
- Melhor para SEO futuro.
- Link facil de entender.
- Pode conviver com a landing.

Riscos:

- Mistura landing, app via `/app/` e loja publica no mesmo dominio.
- Exige cuidado com headers, indexacao e rewrites.
- Pode aumentar complexidade do projeto `confeito-site`.

### Opcao B - `loja.useconfeito.com/[slug]`

Vantagens:

- Isola a loja publica do app privado.
- Reduz risco de colisao com `/app/`.
- Facilita headers, cache e politica de indexacao especificos para loja.
- Pode ser um projeto separado ou modulo publico controlado.
- Mais seguro para separar dados publicos de dados privados.

Riscos:

- Mais um subdominio para configurar.
- Menos concentracao de SEO no dominio raiz.
- Exige comunicacao clara na landing.

### Recomendacao V1

Para a primeira versao real, a decisao de produto e usar `useconfeito.com/loja/[slug]`.

Motivo: o link fica mais claro para cliente final, reforca o dominio principal da marca Confeito e combina melhor com uma vitrine publica elegante.

O app privado continua em `/app/` e deve permanecer separado da loja publica. A rota `/loja/[slug]` nao significa expor o app privado nem ler o payload completo de `public.dados`. A implementacao futura deve servir somente uma projecao publica e sanitizada dos dados da loja, separada de custos, lucro, insumos, movimentos e configuracoes internas.

Se a arquitetura exigir isolamento adicional, `loja.useconfeito.com/[slug]` pode continuar como alternativa tecnica futura. Para a V1 planejada, a referencia de produto e `useconfeito.com/loja/[slug]`.

### Politica de indexacao da loja V1

O app privado em `/app/` deve continuar `noindex`.

A loja publica e diferente do app privado. Ainda assim, na V1, antes de qualidade, legal, seguranca e performance estarem maduros, a recomendacao e considerar iniciar as lojas publicas em `/loja/[slug]` com `noindex`.

Depois de validar fluxo, conteudo, privacidade e performance, a indexacao das lojas pode ser liberada se isso for estrategico. Essa abordagem evita que paginas publicas incompletas sejam indexadas cedo demais.

Nao implementar headers nesta etapa; esta e apenas uma diretriz para a arquitetura futura.

## 12. Segurança e privacidade

Pontos obrigatorios:

- Dados privados do payload nao podem aparecer na loja.
- Custo, lucro, margem, taxa, imposto, insumos e rendimento nunca aparecem para cliente final.
- Somente produtos marcados como publicos aparecem.
- WhatsApp da confeiteira e dado publico quando a loja estiver ativa.
- Dados do cliente no checkout V1 nao precisam ser salvos inicialmente.
- Textos publicos precisam de escape/sanitizacao.
- Nomes, descricoes e observacoes precisam ser tratados contra XSS.
- Fotos precisam ser validadas e servidas de forma segura.
- O payload privado inteiro nunca deve ser lido por uma rota publica.

Riscos atuais observados:

- O app atual salva tudo em um payload por usuario em `public.dados`.
- Esse payload mistura configuracoes, insumos, receitas, precos, estoque e movimentos.
- Fotos atuais sao salvas como data URL dentro do produto.
- A loja publica nao deve consumir esse payload inteiro.
- Uma implementacao direta lendo `payload.produtos` no publico pode expor dados internos sem querer.

## 13. Supabase / dados

O modelo atual usa Supabase Auth no cliente e sincroniza o payload completo do usuario em `public.dados`.

Estrutura observada do payload:

```json
{
  "_ts": 1710000000000,
  "config": {
    "regime": "MEI",
    "aliquota": 0,
    "plano": "Basico",
    "ifoodComissao": 12,
    "ifoodPagamento": 3.2,
    "taxaCartao": 3.5,
    "taxaPix": 0,
    "margem": 30,
    "maoObraHora": 20,
    "produtosMes": 300,
    "custosFixos": [
      { "nome": "Energia + gas", "valor": 80 }
    ]
  },
  "insumos": [
    {
      "id": "i1",
      "nome": "Leite condensado",
      "cat": "Ingrediente",
      "preco": 6.5,
      "qtd": 395,
      "un": "g"
    }
  ],
  "produtos": [
    {
      "id": "p1",
      "nome": "Fatia de bolo de chocolate",
      "rendimento": 10,
      "tempoMin": 60,
      "foto": "data:image/jpeg;base64,...",
      "itens": [
        { "insumoId": "i1", "qtd": 100, "un": "g" }
      ],
      "meuPreco": 0,
      "estoque": 0,
      "alertaEstoque": 3,
      "precos": {
        "iFood": 12,
        "Cartao": 10,
        "Pix / Dinheiro": 9
      },
      "movs": [
        {
          "ym": "2026-6",
          "tipo": "vendeu",
          "qtd": 1,
          "t": 1710000000000,
          "preco": 12,
          "canal": "iFood"
        }
      ]
    }
  ]
}
```

Esse modelo e adequado para o app privado, mas nao e adequado para loja publica segura.

Preferencia tecnica para futuro:

- Criar estrutura publica separada para loja.
- Publicar somente dados sanitizados.
- Nao expor `public.dados.payload`.
- Manter o payload privado como origem interna, mas gerar uma projecao publica.
- Usar RLS cuidadoso.
- Separar leitura publica de escrita privada.
- Evitar service role no client.

Nao criar SQL nesta fase.

## 14. Fases recomendadas

Fase 0 - documentacao e prototipo estatico.

- Criar especificacao.
- Desenhar fluxo.
- Prototipar visual sem dados reais.
- Validar com usuarias.

Fase 1 - area Loja interna, sem loja publica real.

- Aba Loja no app privado.
- Configuracao basica de perfil.
- Selecao de produtos.
- Preview local.
- Sem link publico ainda.

Fase 2 - loja publica com produtos selecionados.

- Criar dados publicos separados.
- Publicar loja por slug.
- Exibir somente produtos marcados como publicos.
- Sem carrinho complexo inicialmente.

Fase 3 - carrinho e WhatsApp.

- Carrinho local.
- Nome e WhatsApp do cliente.
- Retirada/entrega.
- Forma de pagamento.
- Mensagem pronta no WhatsApp.

Fase 4 - categorias/adicionais.

- Categorias configuraveis.
- Adicionais simples.
- Ordenacao manual.
- Destaques.

Fase 5 - pedidos internos/historico.

- Opcionalmente salvar pedidos.
- Historico para a confeiteira.
- Status manual.

Fase 6 - indicacao.

- Link ou codigo individual.
- Recompensa por assinatura paga indicada.
- Regras antifraude basicas.

Fase 7 - assinatura R$19,90.

- Ajuste de posicionamento.
- Trial de 3 meses.
- Plano fundador opcional.

## 15. MVP recomendado

Primeira implementacao real recomendada:

- Aba Loja no Confeito.
- Configurar nome da loja.
- Configurar logo ou foto.
- Configurar WhatsApp.
- Selecionar produtos para aparecerem na loja.
- Definir nome/descricao/preco publico.
- Criar link publico por slug.
- Vitrine publica simples.
- Carrinho simples.
- Envio do pedido para WhatsApp.

O MVP nao deve salvar pedidos no banco se isso atrasar ou aumentar risco. O objetivo e validar se a confeiteira percebe valor e se clientes conseguem pedir.

## 16. Fora da V1

Fica fora da V1:

- Pagamento online.
- Calculo de frete por mapa.
- Login de cliente final.
- Pedido salvo complexo.
- Painel avancado de pedidos.
- Cupons.
- Avaliacao.
- Integracao iFood.
- Impressao.
- Automacao WhatsApp oficial.
- Chat interno.
- Area de entregador.
- Multiloja por conta.

## 17. Impacto no preço

Com a Loja, o Confeito deixa de ser apenas calculadora/gestao e passa a ajudar tambem na venda.

Isso torna mais justificavel o preco de R$19,90 por mes, especialmente com:

- precificacao;
- lucro estimado;
- estoque;
- painel do negocio;
- loja online;
- pedidos pelo WhatsApp.

Recomendacao comercial:

- Manter 3 meses gratis.
- Considerar R$19,90/mes apos o trial.
- Considerar plano fundador de R$14,90 para primeiras usuarias ou lista inicial.
- Usar indicacao para dar meses gratis sem reduzir valor percebido do produto.

## 18. Programa de indicação

Opcoes futuras:

- Indique e ganhe 1 mes gratis quando a pessoa indicada virar assinante pagante.
- Link individual por usuaria.
- Codigo simples para compartilhar.
- Recompensa so depois do primeiro pagamento confirmado.
- Limite de indicacoes pendentes.
- Bloqueio de autoindicacao.
- Revisao manual para casos suspeitos.

Nao implementar na V1 da loja. Pode aparecer como comunicacao futura ou area desabilitada somente depois que assinatura estiver planejada.

## 19. Riscos técnicos

Riscos principais:

- O app atual e um arquivo unico, o que dificulta crescer com rotas publicas complexas.
- O app privado esta em `/app/` e usa noindex; a loja publica provavelmente deve ter outra politica de indexacao.
- O payload privado mistura dados publicos e privados.
- Ler `public.dados.payload` para montar loja publica pode expor custos, insumos, movimentos e configuracoes.
- Fotos em base64/data URL dentro do payload podem pesar muito e piorar performance.
- Muitos produtos com fotos podem estourar localStorage ou deixar a loja lenta.
- Slugs publicos exigem validacao, unicidade e protecao contra enumeracao indevida.
- WhatsApp publico precisa ser consentido pela confeiteira.
- Descricoes, nomes e observacoes exigem escape contra XSS.
- Carrinho local pode ser perdido se o cliente trocar de navegador.
- Link compartilhado precisa funcionar bem em mobile.
- Separacao entre app privado e loja publica precisa ser clara no codigo, nos dados e nos headers.

## 20. Recomendação final

Nao implementar a Loja Confeito inteira de uma vez.

A melhor sequencia e:

1. Fechar especificacao e prototipo visual.
2. Definir modelo publico separado de dados.
3. Criar area Loja interna sem publicacao real.
4. Publicar somente produtos selecionados e sanitizados.
5. Adicionar carrinho local e WhatsApp.
6. Medir uso antes de salvar pedidos complexos.
7. So depois conectar assinatura e indicacao.

Conclusao executiva:

A Loja Confeito tem potencial alto para aumentar valor percebido e justificar R$19,90/mes, porque transforma o Confeito em uma ferramenta de gestao e venda. Mas a implementacao precisa priorizar seguranca: o payload atual nao deve ser exposto publicamente. A V1 deve nascer simples, bonita e separada dos dados privados.

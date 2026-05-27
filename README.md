# Voll Bank - Régua de Cobrança Inteligente 2.0

Demo executiva de régua de cobrança inteligente inspirada em uma experiência de produto por perfil de cliente.

A interface demonstra como a cobrança pode mudar conforme o perfil do devedor, usando jornadas, canais, eventos de tracking e próxima ação recomendada.

## Perfis demonstrados

- Novo Cliente
- Bom Pagador
- Pagador Duvidoso
- Mau Pagador

Cada perfil possui uma cadência própria antes, no dia e depois do vencimento.

## Principais recursos

- Interface "Como a régua funciona" com abas por perfil.
- Linha do tempo de acionamentos por etapa da régua.
- Canais: E-mail, SMS, WhatsApp, humano/crédito.
- Carteira simulada de clientes com perfil, atraso, valor, último evento e próxima ação.
- Decisão automática de canal e racional da recomendação.
- Template de mensagem adaptado ao perfil do cliente.
- Link rastreável conceitual para registrar clique e redirecionar para WhatsApp.
- Simulação de eventos como `EMAIL_CLICKED` e `PAYMENT_DONE`.
- Painel técnico recolhido com payloads e testes de conectividade.
- Integração mantida com o proxy Render em `/api/regua-cobranca`.

## Fluxo de tracking

O botão de e-mail ou WhatsApp deve apontar para uma URL intermediária:

```txt
Botão do e-mail
→ /track/whatsapp-click?token=...
→ registra EMAIL_CLICKED ou WHATSAPP_STARTED
→ redireciona para WhatsApp ou portal de renegociação
```

Esse desenho permite medir clique de forma mais confiável do que abertura de e-mail por pixel.

## Como usar

Abra o `index.html` em um navegador ou publique o repositório em um host estático.

1. Escolha um perfil de cliente.
2. Veja a linha do tempo da régua para aquele perfil.
3. Selecione um cliente na carteira.
4. Revise a decisão automática, o racional e a mensagem sugerida.
5. Simule clique/pagamento ou envie a ação selecionada.
6. Use o painel técnico para validar payloads e conectividade.

## Integração

A página envia os acionamentos para:

```txt
https://demo-cob-bancoabc.onrender.com/api/regua-cobranca
```

As ações válidas continuam sendo:

```txt
EMAIL
SMS
WHATSAPP
```

## Versão

Branch: `v2.0`

Objetivo da versão: evoluir a demo de botões de disparo para uma experiência de régua inteligente por perfil de cliente, com cadência, tracking e automação de próxima ação.

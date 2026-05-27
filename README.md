# Voll Bank - Régua de Acionamentos 2.0

Demo executiva de régua inteligente de cobrança para simular uma jornada omnichannel com recomendação de canal, mensagem sugerida e envio real para o proxy de acionamentos.

## Principais recursos

- Painel executivo com valor em aberto, dias em atraso, risco e próximo canal recomendado.
- Motor simples de recomendação para escolher entre E-mail, SMS e WhatsApp.
- Jornada visual em cinco etapas: aviso cordial, lembrete, negociação assistida, oferta personalizada e escalonamento humano.
- Templates humanizados por canal, com destaque para abordagem calorosa e profissional no WhatsApp.
- Histórico simulado usado como contexto da recomendação.
- Integração mantida com o endpoint Render em `/api/regua-cobranca`.
- Painel técnico recolhido com logs, cópia do último payload e testes reais de conectividade.

## Como usar

Abra o `index.html` em um navegador ou publique o repositório em um host estático.

1. Edite os dados do cliente.
2. Clique em `Recomendar próximo acionamento`.
3. Revise a mensagem sugerida.
4. Envie por E-mail, SMS ou WhatsApp.
5. Use o painel técnico apenas quando precisar validar payloads ou conectividade.

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

Objetivo da versão: evoluir a demo de botões de disparo para uma experiência de régua inteligente, com recomendação contextual, narrativa comercial e maior percepção de produto.

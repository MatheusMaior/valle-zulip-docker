# Distribuição Valle Chat

Este branch contém o empacotamento administrado pela Valle Monterei para o chat interno.
O servidor é construído exclusivamente de um commit fixado do branch `valle-12.2` em
`MatheusMaior/valle-zulip`; produção não usa a imagem publicada pelo Zulip.

Use sempre os dois arquivos:

```bash
docker compose -f compose.yaml -f compose.valle.yaml build zulip
docker compose -f compose.yaml -f compose.valle.yaml up -d --wait
```

O arquivo `.env` local fornece os segredos. O Compose Valle desliga serviços externos do
fabricante, não publica portas diretamente e conecta apenas o container web à rede do
Traefik.

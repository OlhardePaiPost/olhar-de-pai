# Olhar de Pai — publicação automática

Este repositório guarda os reels e publica um por dia no Instagram pelo GitHub Actions.

- `calendario.csv` — o que sai em cada data (id, data, horário, tipo, arquivos, frase, legenda)
- `reels/` e `carrosseis/` — as mídias (o GitHub Pages as deixa públicas, o Instagram busca por lá)
- `publicar.py` — script que publica pela API oficial da Meta
- `.github/workflows/postar.yml` — roda todo dia às 12h e 19h (Brasília)
- `postado.csv` — registro do que já foi publicado (criado sozinho)

## Segredos necessários (Settings > Secrets and variables > Actions)
| Onde | Nome | Valor |
|---|---|---|
| Secrets | `IG_TOKEN` | token de acesso gerado no painel do app da Meta |
| Secrets | `IG_USER_ID` | id numérico da conta do Instagram (aparece no mesmo painel) |
| Variables | `BASE_URL` | `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO` (sem barra no fim) |

## Testar (Actions > postar-no-instagram > Run workflow)
1. modo `verificar` — confirma que o token e o id funcionam. Não publica nada.
2. modo `simular` — lista o que publicaria hoje.
3. modo `publicar` com `id` = R004 — publica o reel do dia 4 agora (teste real).

## Se algo der errado
- "Arquivo não acessível": o GitHub Pages ainda não publicou (espere 2 min) ou a pasta não foi enviada.
- Erro de token: gere outro token no painel do app e troque o segredo `IG_TOKEN`.
- O workflow avisa em amarelo se o Instagram devolver um token diferente ao renovar: troque o segredo pelo novo.

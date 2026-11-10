# MMH Themes

Temas do Home Assistant no padrão visual **My Magic Home** (Direção estética 2026).
Feitos para trabalhar junto com os **MMH Cards**.

| Tema | Uso |
|---|---|
| `mmh-premium` | Padrão: vidro grafite com desfoque sobre a foto de fundo |
| `mmh-premium-lite` | Mesmas cores, **sem desfoque**: tablets de parede mais fracos |

## Instalação

1. **Pré-requisito:** [card-mod](https://github.com/thomasloven/lovelace-card-mod) instalado pelo HACS.
2. No `configuration.yaml`:
   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```
3. HACS → ⋮ → Repositórios personalizados → este repositório, categoria **Tema** → Baixar.
4. Ferramentas do desenvolvedor → Ações → `frontend.reload_themes`.
5. Perfil (ou o dashboard) → Tema → **mmh-premium**.

## O que muda por cliente (sem editar o tema)

O HACS sobrescreve o tema a cada atualização, então nada de cliente fica nele.
Coloque os arquivos em `/config/www`:

| Arquivo | Uso |
|---|---|
| `backgrounds/desktop/fundo00.webp` … `fundo03.webp` | Fundo acima de 1024 px |
| `backgrounds/tablet/fundo00.webp` … | Fundo de 601 a 1024 px |
| `backgrounds/mobile/fundo00.webp` … | Fundo até 600 px |
| `backgrounds/logo-mmh-oficial.png` | Logo no topo |

`fundo00` é o fundo padrão. Para uma view usar outro, no YAML da view:
```yaml
background: center / cover no-repeat var(--mmh-bg-fundo01) fixed
```

## Trocar as cores sem editar o tema

Com o **MMH Cards** instalado, o card `custom:mmh-cores` ("Cores da casa")
escolhe paletas prontas ou cores próprias e aplica por cima deste tema, na casa
toda. Ver a documentação do card no MMH Cards.

## Paleta

| Token | Papel | Valor |
|---|---|---|
| `mmh-destaque-rgb` | Azul My Magic Home: ações e ligado | `#5A868C` |
| `mmh-destaque-claro-rgb` | Azul-claro: palavras-chave e números | `#C3D8D9` |
| `mmh-luz-rgb` | Âmbar: **só iluminação** | `#CB9564` |
| `mmh-texto-rgb` | Off-white | `#F4F4F4` |
| `mmh-vidro` | Grafite quente translúcido | `rgba(58, 51, 45, 0.52)` |
| `mmh-linha` | Bordas | `rgba(244, 244, 244, 0.08)` |

## Licença

Uso exclusivo em instalações de clientes My Magic Home. Veja [LICENSE](LICENSE).

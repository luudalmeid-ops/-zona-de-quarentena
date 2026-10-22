# Zona de Quarentena

Jogo de triagem em pixel art feito pela **Valtore**. Você é o fiscal do Portão Leste da Zona 7: ouve cada sobrevivente no portão, examina e decide quem salvar e quem eliminar, enquanto mantém o muro, a comida, a saúde e a energia da base.

## Jogar

- **No navegador / iPhone:** https://luudalmeid-ops.github.io/-zona-de-quarentena/
  No iPhone, abra no Safari → Compartilhar → **Adicionar à Tela de Início**.
- **Android:** baixe [`android/ZonaDeQuarentena.apk`](android/ZonaDeQuarentena.apk) e instale (permita "apps desconhecidos").

## Arquivos

| Caminho | O que é |
|---|---|
| `index.html` | O jogo inteiro (HTML, CSS e JavaScript, sem dependências) |
| `manifest.json`, `sw.js`, `icon-*.png` | Instalação na tela inicial e funcionamento offline |
| `android/` | Código do app Android (WebView), script `build_apk.py` e o APK |
| `android/icone/desenhar_icone.py` | Gera os ícones em pixel art |

## Gerar o APK

```
python3 android/build_apk.py --android-all android-all.jar --dx dx.jar \
  --keystore chave.p12 --storepass SENHA --out android/ZonaDeQuarentena.apk
```

`android-all.jar` (org.robolectric:android-all, API 29) e `dx.jar` (com.jakewharton.android.repackaged:dalvik-dx) vêm do Maven Central. A chave de assinatura não fica no repositório: atualizações precisam ser assinadas com a mesma chave.

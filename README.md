# Zona de Quarentena

Jogo de triagem em pixel art feito pela **Valtore**. Você é o fiscal do Portão Leste da Zona 7 e tem **10 dias** até a cura.

- **De dia, no portão:** ouve cada sobrevivente, examina e decide quem salvar e quem eliminar.
- **À noite, no refeitório:** os 20 moradores trazem reclamações, pedidos e acusações de infecção (às vezes só medo). Você examina, isola, defende ou executa, e pode expulsar quem pesa na comida.
- **Facções:** Humanistas querem salvar todos; Pragmáticos, só os úteis. Qualquer uma em zero é motim.
- **A cura** depende de cientistas e médicos vivos. Vários finais, conforme suas escolhas.
- **Selos de liderança:** antes do primeiro dia você escolhe como vai liderar (Coração aberto, Cabeça fria, Olho clínico ou Mão de ferro). No fim, o jogo mostra como você liderou de verdade.
- **Grupos e famílias:** casais, pais com filhos e avós com netos chegam juntos. Cada um passa pela triagem, e separar uma família tem consequência à noite.
- **Recusar:** dá para mandar alguém embora no portão, sem exame, ou depois da triagem. Não conta erro, mas a base perde quem poderia ajudar.
- Crianças e idosos comem 1,5 ração por dia. O gerador entra em colapso no dia 5.
- **Mão de obra:** cada profissional precisa de um ajudante adulto sem profissão; sem ajudante, produz metade.
- **Acampamento da resistência:** quem você recusa ou expulsa vai para fora. Com família aqui dentro, eles podem invadir. Dá para armar um guarda no portão (que pode ser leal ou traidor) e desarmá-lo pelo registro.
- **Encapuzados:** a partir do dia 4, não aceitam exame. Oferecem o recurso em crise; você decide pela conversa. Podem ser normais, ladrões, informantes do acampamento ou infectados.
- **Vírus mais forte:** contágio maior dentro da base, e o sintoma só aparece na segunda noite.
- O progresso é salvo ao fim de cada noite.
- **Português e inglês:** escolha na tela de abertura (o padrão segue o idioma do aparelho).

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

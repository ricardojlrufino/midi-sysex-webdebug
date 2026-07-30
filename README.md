# MIDI SysEx WebDebug

Ferramenta web para capturar, agrupar e rotular mensagens SysEx MIDI recebidas de qualquer dispositivo MIDI, direto no navegador via [Web MIDI API](https://developer.mozilla.org/en-US/docs/Web/API/Web_MIDI_API). Não requer instalação — é um único arquivo HTML.

▶️ **[Abrir a ferramenta (GitHub Pages)](https://ricardojlrufino.github.io/midi-sysex-webdebug/)**

## Funcionalidades

- Conecta a qualquer porta MIDI de entrada disponível no sistema (via Web MIDI, com suporte a SysEx).
- Reagrupa mensagens fragmentadas de SysEx automaticamente.
- Agrupa pacotes recebidos próximos no tempo (janela configurável), útil quando uma única ação do dispositivo gera várias mensagens.
- Permite rotular cada pacote capturado (slot/módulo, ação, efeito, parâmetro, valor, notas) para documentar o protocolo do dispositivo.
- Histórico local (`localStorage`) com exportação para Markdown ou JSON.

## Como usar

1. Abra a página em um navegador com suporte a Web MIDI (Chrome ou Edge), servida via `http://` ou `https://` (não funciona em `file://`).
2. Clique em **Conectar Web MIDI** e conceda a permissão de acesso MIDI.
3. Selecione a porta de entrada do dispositivo MIDI.
4. Acione algo no dispositivo (troca de preset, ajuste de parâmetro etc.) — os pacotes SysEx capturados aparecem em **Preview dos pacotes recentes**.
5. Selecione os pacotes relevantes, preencha o rótulo e clique em **Salvar pacote rotulado** (ou **Salvar sem rótulo**).
6. Exporte o histórico acumulado em Markdown ou JSON para documentar o protocolo do dispositivo.

## Rodando localmente

Por exigir `http(s)://`, sirva o arquivo com qualquer servidor estático simples, por exemplo:

```bash
python3 -m http.server 8000
```

E acesse `http://localhost:8000/index.html`.

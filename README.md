# ✈️ Mover Áudios para Pastas de Aeroportos (Google Apps Script)

Este script em **Google Apps Script** foi desenvolvido para automatizar a organização de arquivos de áudio no Google Drive, movendo cada um deles para a pasta correta com base no **aeroporto associado à entrevista**. Ele utiliza uma **planilha de controle** com abas auxiliares para mapear os dados e evitar duplicações.

---

## 📂 Funcionalidade

- Verifica os arquivos `.mp3` em uma pasta de origem.
- Extrai o **ID da entrevista** do nome do arquivo.
- Verifica na aba **Auxiliar** qual é o **aeroporto** correspondente ao ID.
- Com base no mapeamento de aeroportos e pastas, move o áudio para a **pasta de destino correta**.
- Registra os arquivos processados na aba **Retorno**, com o link do novo local.

---

## 🧱 Estrutura da Planilha Esperada

### Abas obrigatórias:
- `Auxiliar`: Contém o **ID da entrevista** na primeira coluna e o **ID do aeroporto** na segunda.
- `Retorno`: Registra os **IDs processados** e os **links dos áudios copiados**. A verificação de duplicação é feita aqui.

---

## 📌 Pré-requisitos

- Uma planilha do Google com as abas citadas acima.
- Uma pasta de origem com os áudios `.mp3` no Google Drive.
- IDs válidos das pastas de destino no Google Drive (uma para cada aeroporto).
- Permissões adequadas para leitura e escrita no Drive e Planilhas.

---

## 🛠 Como usar

1. Abra o **Google Apps Script** a partir da planilha.
2. Cole o código no editor.
3. Configure os seguintes pontos no código:
   - O **ID da pasta de origem** dos áudios.
   - Os **IDs das pastas de destino** (no objeto `idsPastasAero`).
4. Execute a função `moverAudiosParaDestino()` manualmente ou configure um gatilho automático.

---

## 🚨 Observações

- O script assume que o **ID da entrevista está no início do nome do arquivo**, separado por espaço.
- Já processados não serão copiados novamente, evitando duplicidade.
- Os erros de cópia ou falta de mapeamento são registrados no log via `Logger.log`.

---

## 📁 Exemplo de nome de arquivo válido

```
12345678 Audio.mp3
```

Neste caso, `12345678` será identificado como o ID da entrevista.


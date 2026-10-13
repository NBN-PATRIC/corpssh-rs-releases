# CorpSSH RS: instaladores

Cliente SSH, SFTP e túneis da NBN Telecom para Windows. É um fork do
[CorpSSH](https://github.com/alcirhagge/corpssh) (MIT, de alcirhagge) com o backend reescrito em Rust (Tauri 2 + russh).

Este repositório **só publica as versões assinadas**. O app instalado consulta o `latest.json` da última versão e se
atualiza sozinho. O código-fonte fica num repositório privado da NBN.

## Instalar

1. Baixe o `CorpSSH-RS_x.y.z_x64-setup.exe` da [última versão](../../releases/latest).
2. Execute. A instalação é por usuário e não pede administrador.
3. Na primeira abertura, o app importa sozinho os dados do CorpSSH antigo (`~/.corpssh`), inclusive as senhas salvas. A pasta antiga não é alterada.

O instalador não tem certificado comercial de assinatura de código. Por isso o SmartScreen pode avisar
"O Windows protegeu o seu PC": clique em **Mais informações** e depois em **Executar assim mesmo**. Para conferir o
arquivo, compare o hash com o `SHA256SUMS-windows.txt` da versão:

```powershell
Get-FileHash .\CorpSSH-RS_x.y.z_x64-setup.exe -Algorithm SHA256
```

## Atualização automática

O app procura versão nova ao abrir, baixa em segundo plano e instala quando você fecha o app, ou na hora pelo aviso
"atualizar agora". Cada versão é assinada, e o app recusa pacote sem a assinatura da NBN.

## Licença

MIT. Interface e ideia originais do CorpSSH, de alcirhagge.


# 📦 Guia de Instalação e Importação de VPN no Windows (OpenVPN GUI)

Este guia explica como instalar o OpenVPN e importar seu perfil de VPN utilizando o recurso **Import file** — sem a necessidade de copiar manualmente os arquivos para a pasta `config`.

---

## ✅ 1. Instalar o OpenVPN no Windows

1. Acesse o site oficial:  
   [https://openvpn.net/community-downloads/](https://openvpn.net/community-downloads/)

2. Baixe a versão para **Windows 64-bit** (MSI Installer).

3. Execute o instalador como **Administrador** e siga os passos para concluir.

---

## 📦 2. Preparar os Arquivos

Você deve ter recebido um arquivo `.zip` com o nome do seu e-mail, por exemplo:

```
devops@skymed.app.br.zip
```

Este `.zip` deve conter:

- `devops@skymed.app.br.ovpn` → Arquivo de configuração
- `devops@skymed.app.br.crt` → Certificado do cliente
- `devops@skymed.app.br.key` → Chave privada do cliente

> Extraia os arquivos para uma pasta temporária, como:  
> `C:\Users\SeuNome\Downloads\VPN`

---

## 📥 3. Importar o Perfil VPN (usando OpenVPN GUI)

1. No menu Iniciar, procure **OpenVPN GUI**.
2. Clique com o **botão direito** e selecione **Executar como administrador**.
3. Um ícone com um monitor e cadeado aparecerá na **bandeja do sistema** (canto inferior direito da tela).
4. Clique com o **botão direito** neste ícone.
5. Selecione **Import file...**
6. Navegue até a pasta onde extraiu os arquivos.
7. Selecione o arquivo `.ovpn` e clique em **Abrir**.

> O OpenVPN copiará automaticamente os arquivos necessários para `%USERPROFILE%\OpenVPN\config`.

---

## 🔌 4. Conectar à VPN

1. No mesmo ícone do OpenVPN na bandeja:
2. Clique com o botão direito > selecione o perfil importado (ex: `devops@skymed.app.br`)
3. Clique em **Conectar**

---

## 🛠️ 5. Solução de Problemas

- **Erro de certificado**: verifique se os arquivos `.crt` e `.key` estão no mesmo diretório do `.ovpn` no momento da importação.
- **Erro de caminho**: o `.ovpn` deve usar caminhos relativos, como:
  ```
  cert devops@skymed.app.br.crt
  key devops@skymed.app.br.key
  ```
  e **não** caminhos absolutos como `C:\usuário\documentos\...`.

---

## ✅ Conexão Estabelecida!

Se tudo estiver correto, você verá uma notificação informando que a VPN foi conectada com sucesso.

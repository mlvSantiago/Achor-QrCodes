# Gerador Automatico de QrCodes

Este script em Python lê uma planilha Excel com dados de ramais SIP e gera QR Codes personalizados.
---

## 📘 Descrição
O objetivo do script é automatizar a criação de QR Codes configuráveis para provisionamento rápido de contas SIP.

Ele lê uma planilha .xlsx contendo os campos necessários, monta um JSON com as informações SIP e gera uma imagem contendo:

- O QR Code com os dados

- A logo da empresa inserida no centro

- O nome do usuário (display) alinhado abaixo do código

Cada QR Code é salvo individualmente com o nome correspondente ao display.
---

## ⚙️ Funcionamento do Script

1. O programa recebe o nome de uma planilha .xlsx como argumento (sem extensão).

2. Lê o arquivo usando pandas.

3. Para cada linha da planilha, extrai:

- username

- password

- display

4. O usuário informa pelo terminal o subdomain (Ex: rj01inter.achortechnologies.com.br:4319).

5. O script monta o JSON SIP no formato:

```bash
{
  "sipaccounts": [
    {
      "sipusername": "xxxx",
      "sippassword": "xxxx",
      "subdomain": "xxxx"
    }
  ]
}
```

6. Gera o QR Code contendo o JSON.

7. Insere a logo no centro do QR Code.

8. Adiciona o display como texto abaixo.

9. Salva cada imagem em: 

```bash

./qrCodes/<display>.png

```
---

## 🚀 Como Executar

No Terminal: 

```bash
python gerar_qr.py planilha
```
Não é nescessario incluir .xlsx no nome.

O script então solicitará:

```bash
Entre com o Subdomain dos QrCodes:
```
Digite o subdominio desejado e aperte enter.
---
## 🧰 Requisitos

Pacotes nescessarios:
```bash
python -m pip install pandas qrcode pillow openpyxl
```
---

## 🖼️ Saída gerada
Para cada linha da planilha, gera-se um arquivo PNG contendo:

- QR Code com os dados SIP

- Logo centralizada

- Texto (display) abaixo

- Resolução ajustada automaticamente

![QR Code gerado](assets/Apto 101 A.png)



---


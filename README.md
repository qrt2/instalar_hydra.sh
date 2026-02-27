# Hydra Installer for Termux (Android 12+ Fix)

Este repositório contém um script de automação para instalar o **THC-Hydra** no Termux. O diferencial deste instalador é a aplicação automática de um patch no código-fonte para corrigir o erro de `Aborted (fdsan)`, comum em versões recentes do Android (12, 13, 14+).

## O que o script faz?

1.  **Instala Dependências:** Configura o ambiente com `clang`, `make`, `libssh`, `openssl` e outras bibliotecas essenciais.
2.  **Corrige o Erro de fdsan:** Injeta uma instrução no `hydra.c` para desativar o monitoramento de File Descriptors do Android que causa o fechamento repentino do app.
3.  **Compilação Nativa:** Compila o Hydra diretamente no seu hardware para máxima performance.
4.  **Instalação Limpa:** Move o binário para o seu `$PREFIX/bin` permitindo o uso global do comando `hydra`.

## 👤 Créditos e Contato

Desenvolvido por **@cyber**

Para suporte, dúvidas ou atualizações, entre em contato via Telegram:
https://t.me/cybe4

## Como Instalar

Basta copiar e colar o comando abaixo no seu Termux:

```bash
apt update && pkg upgrade -y -o Dpkg::Options::="--force-confnew" && pkg install curl -y && curl -LO https://raw.githubusercontent.com/qrt2/instalar_hydra/main/termux_hydra && chmod +x termux_hydra && ./termux_hydra

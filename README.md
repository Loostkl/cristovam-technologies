# LostBoost

App de otimização para **Windows 10 e 11** voltado a jogos: ajustes do Windows com desfazer, **Modo Jogo** que prepara o PC sozinho quando um jogo abre, limpeza, monitoramento, testes de mouse, teclado, controle e monitor, e overlay de FPS.

## Baixar

Baixe o instalador na página de [**Releases**](https://github.com/Loostkl/cristovam-technologies/releases), em *Assets*: o arquivo `LostBoost-Setup-<versão>.exe`.

> **Primeira versão.** O programa ainda não foi validado em muitos computadores. Se algo não funcionar, abra uma *issue* aqui (veja [Problemas](#problemas)).

## Requisitos

- Windows 10 ou 11, 64 bits.
- Permissão de administrador (o programa precisa para ler temperaturas e aplicar os ajustes; o Windows pergunta ao instalar e ao abrir).
- Microsoft Edge WebView2 (a janela do app). O Windows 11 já tem; se o seu Windows 10 não tiver, o instalador oferece baixar da Microsoft.
- Não precisa instalar Python nem nenhum outro programa.

## Como instalar

1. Baixe o `.exe` e dê dois cliques.
2. Se o Windows mostrar **"Editor desconhecido"** ou **"O Windows protegeu o computador"**, clique em *Mais informações* e depois em *Executar assim mesmo*. Isso acontece porque o instalador ainda não tem assinatura digital de um editor verificado.
3. Siga o assistente: termos, pasta, opções (atalho na área de trabalho e início com o Windows são opcionais).
4. Ao abrir, aceite o pedido de administrador.

### Conferir o arquivo (opcional)

A página de cada release mostra o **SHA-256** do instalador. No PowerShell, na pasta do arquivo:

```powershell
Get-FileHash .\LostBoost-Setup-<versão>.exe -Algorithm SHA256
```

O resultado deve ser igual ao da página do release.

## O que ele faz

- **Dashboard:** Modo Gamer (liga e desliga um conjunto seguro de ajustes), "Otimizar agora", saúde do sistema e latência de rede.
- **Modo Jogo:** reconhece o jogo que abriu, aplica as ações que você escolher (prioridade, memória, plano de energia, overlay de FPS) e **desfaz tudo quando o jogo fecha**. Perfil por jogo e relatório de cada sessão.
- **Otimização:** ajustes do Windows por grupo, cada um com risco informado e desfazer.
- **Tarefas e Processos:** limpeza de memória e DNS (manual ou automática), apps de inicialização, prioridade e núcleos por programa, regras por jogo.
- **Testes:** mouse e teclado (cliques por segundo, apertos duplos, reação), controle (deriva, alcance, gatilhos, vibração), monitor (pixels mortos, ghosting, taxa de atualização) e conversor de sensibilidade entre jogos.
- **Programas e Áudio:** instala e atualiza programas de uma vez (winget), desinstala usando o desinstalador oficial, controla volume e microfone.
- **Overlay de FPS** (PresentMon), **Limpeza** de arquivos temporários e caches.

O programa **não promete ganho de FPS**: ele mostra o que mediu. Nada é fechado, apagado ou desinstalado sem você escolher, e sistema, antivírus e anti-cheat são deixados em paz.

## Segurança e privacidade

- Cada ajuste guarda o valor original e tem desfazer; um ponto de restauração do Windows é criado antes do primeiro. A única exceção é a **limpeza de arquivos**, que não tem volta.
- O programa **não envia seus dados** para lugar nenhum. Ele só usa a internet quando você pede (baixar o medidor de FPS, instalar ou atualizar programas pelo winget) e para medir a latência de rede com conexões curtas a `1.1.1.1` (Cloudflare), sem enviar nada seu.
- Nenhum código é injetado em jogos. Mesmo assim, nenhuma ferramenta pode garantir que todo sistema anti-cheat vai aceitá-la: em jogos competitivos, use por sua conta e risco.
- Os dados do programa ficam em `%APPDATA%\Otimizador`.

## Desinstalar

*Configurações do Windows > Aplicativos > LostBoost > Desinstalar.* Antes, abra o programa e use "Desfazer" nos ajustes que aplicou. O desinstalador pergunta se você quer apagar também os dados do programa (padrão: manter).

## Problemas

Abra uma [*issue*](https://github.com/Loostkl/cristovam-technologies/issues) com:

- a versão do programa (Configurações > Sobre o app) e do Windows;
- o passo a passo para repetir o problema, o que esperava e o que aconteceu.

**Não anexe dados pessoais.** O arquivo `erro.log` (em `%APPDATA%\Otimizador`) pode conter nomes de pastas e do seu usuário: revise antes de anexar.

## Sobre este repositório

Este repositório existe só para distribuir o instalador e receber relatos de problemas. O código-fonte não é público.

## Licença

O programa é **gratuito para uso pessoal e não comercial**. Não é permitido vender, redistribuir o instalador (compartilhe o link desta página), usar em empresas ou lan houses, nem modificar ou descompilar o programa sem autorização por escrito. Os termos completos aparecem no instalador, e a lista de componentes de terceiros fica em `AVISOS-DE-TERCEIROS.txt`, na pasta onde o programa for instalado.

# App do iPhone — Márcia Colmati Semijoias (lançar venda e compra)

O que é: um app nativo (SwiftUI) que mostra a mesma tela de lançamentos do sistema, adaptada ao iPhone, e conversa com o seu Apps Script. Abre com a animação da logo. Protege o acesso com Face ID / senha do iPhone.

> **Aviso honesto:** este projeto foi escrito e testado na parte da tela e do servidor, mas **não foi compilado nem rodado em um iPhone** (não existe Mac/Xcode no ambiente onde eu trabalho). A compilação acontece no GitHub (passo 3). Se algo falhar, copie a mensagem de erro e me envie — eu corrijo.

## Passo 1 — Atualizar o Apps Script (v1.7.0)
1. Substitua os arquivos alterados e crie o **novo arquivo `ApiMovel`** (tipo Script) com o conteúdo de `ApiMovel.gs`.
2. Confira `appsscript.json` (igual ao do pacote).
3. Execute **`instalar`** uma vez.
4. **Nova implantação só para o app:** *Implantar › Nova implantação › Aplicativo da Web* → **Executar como: Eu (rccolmat@gmail.com)** e **Quem tem acesso: Qualquer pessoa**. Copie a URL que termina em `/exec`.
   - A implantação da equipe (usuário que acessa) continua como está. Depois, em *Gerenciar implantações*, confira que cada uma manteve sua configuração.
5. Abra o sistema web › **Configurações › App do iPhone**, digite um nome (ex.: "iPhone da Márcia") e **Gerar código de acesso**. Anote o código (aparece uma vez).

## Passo 2 — Colocar o projeto no GitHub
1. Crie uma conta em github.com e um repositório **privado** (ex.: `colmati-app`).
2. Envie **todo o conteúdo desta pasta** (arrastando os arquivos na página do repositório, *Add file › Upload files*). Precisa ir a pasta oculta `.github` (se o navegador não a incluir, use o GitHub Desktop ou `git push`).

## Passo 3 — Gerar o .ipa
1. No repositório: aba **Actions › Gerar .ipa › Run workflow** (ou o próprio envio já dispara).
2. Aguarde uns 5 a 10 minutos. Ao terminar, abra a execução e baixe o arquivo **Colmati-ipa** (um .zip com `Colmati.ipa` dentro).
3. Se der erro vermelho, abra o passo que falhou, copie o texto do erro e me envie.

## Passo 4 — Instalar com o Sideloadly
1. No iPhone: *Ajustes › Privacidade e Segurança › Modo de Desenvolvedor* → ligar (reinicia).
2. Abra o Sideloadly, conecte o iPhone, arraste o `Colmati.ipa`, informe seu Apple ID e clique em **Start**.
3. No iPhone: *Ajustes › Geral › VPN e Gerenciamento de Dispositivo* → confie no seu Apple ID.
4. Com Apple ID gratuito o app **vence em 7 dias**: reinstale pelo Sideloadly (mantendo o mesmo Apple ID e o mesmo ID do app, os dados e o código ficam).

## Passo 5 — Primeiro uso
Abra o app → informe a **URL /exec** (Passo 1.4) e o **código de acesso** (Passo 1.5) → Conectar. Pronto: *Nova venda* e *Nova compra*.

## O que o app faz (e não faz)
- Faz: nova venda (cliente com busca e cashback, itens com busca e foto, forma de pagamento, parcelas, plano de recebimento do PIX parcelado, desconto, avisos de estoque/preço abaixo do custo) e nova compra (itens, categoria, custo, despesas, preço, **foto pela câmera ou galeria**, último código cadastrado com atalho "usar próximo").
- Não faz: editar, cancelar, devolver, análises, estoque e A Receber (continuam no sistema web).
- Precisa de internet.

## Atualizações futuras
Quando eu mudar os formulários do sistema, gero de novo a pasta `App/www` e você substitui no GitHub e gera novo .ipa.

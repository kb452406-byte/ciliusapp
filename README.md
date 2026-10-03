# Cílios Liss — app de celular (PWA)

Lê a **Planilha Google** e o **Google Agenda** da sua conta e mostra os ganhos por **ano → mês → dia**.
Instala na tela inicial do celular (Android e iPhone) e abre como um app.

## 1) Publicar o app (precisa ser HTTPS)
Suba esta pasta em qualquer hospedagem gratuita: **Netlify Drop** (arraste a pasta em app.netlify.com/drop),
**GitHub Pages** ou **Cloudflare Pages**. Você receberá um endereço tipo `https://seuapp.netlify.app`.

## 2) Google Cloud
1. Ative **Google Sheets API** e **Google Calendar API**.
2. Tela de consentimento OAuth → Externo → adicione seu e-mail em *Usuários de teste*.
3. Credenciais → ID do cliente OAuth → **App da Web**.
4. Em **Origens JavaScript autorizadas** coloque o endereço do passo 1 (sem barra no final).
5. Copie o **Client ID**.

## 3) Usar no celular
1. Abra o endereço no celular → menu do navegador → **Adicionar à tela inicial**.
2. Aba **Config**: cole Client ID, ID da planilha, intervalo (ex.: `Página1!A1:K2000`) e ID da agenda (`primary`).
3. Toque em **Conectar com Google** e aceite as permissões (somente leitura).

## Colunas da planilha
`Data` (dd/mm/aaaa), `Cliente`, `Procedimento`, `Modelo`, `Forma de Pagamento`, `Valor`, `Zama`, `Sarah`, `CíliosLiss`.
Se `Data` estiver vazia, usa `Ano` e `Mês`. Se a divisão estiver vazia, calcula: atendente 20% até 2025 e 10% a partir de 2026; o resto 50/50.
Nomes das colunas de pessoas: edite `NOMES` no topo do script em `index.html`.

## Privacidade
Sem servidor próprio: o app fala direto com as APIs do Google. A última leitura da planilha fica salva no aparelho para abrir offline.

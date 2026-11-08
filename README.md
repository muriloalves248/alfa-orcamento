# Alfa — Orçamento Elétrico (PWA)

## Arquivos
- `index.html`: aplicação completa (HTML, CSS e JavaScript).
- `manifest.json`: metadados de instalação.
- `sw.js`: cache offline.
- `icons/`: ícones SVG.

## Hospedagem gratuita no GitHub Pages
1. Crie um repositório público no GitHub, por exemplo `alfa-orcamento`.
2. Envie todos os arquivos e a pasta `icons` para a raiz do repositório.
3. Abra **Settings → Pages**.
4. Em **Build and deployment**, escolha **Deploy from a branch**.
5. Selecione `main` e `/ (root)`, depois salve.
6. Aguarde a publicação e abra o endereço `https://SEU-USUARIO.github.io/alfa-orcamento/` no Chrome do Android.
7. No menu do Chrome, escolha **Instalar app** ou **Adicionar à tela inicial**.

Também pode publicar a pasta na Netlify (Add new site → Deploy manually) ou Vercel. O site precisa estar em HTTPS para service worker/PWA funcionar.

## Uso offline e dados
Abra o app online uma primeira vez para o service worker armazenar os arquivos. Depois, o app abre sem internet. Os orçamentos e preços ficam no `localStorage` do navegador/aparelho. Use **Exportar backup JSON** regularmente para guardar uma cópia; limpar os dados do navegador pode apagar os registros. Backup/importação não sincroniza aparelhos.

## Observações técnicas importantes
- Esta versão usa CSS próprio, sem CDN externo, para que a interface funcione offline desde o primeiro carregamento após o cache.
- Os preços iniciais são exemplos editáveis, não uma tabela de mercado.
- O valor por item é mão de obra; materiais não são somados automaticamente.
- O kVA é estimado por `W / FP / 1000`, com FP configurável. Isso não é dimensionamento normativo de condutores ou proteções.
- Não calcula seção de cabos, corrente de projeto, método de instalação, agrupamento, queda de tensão, curto-circuito, seletividade, demanda ou coordenação DR/DPS. Faça o projeto e as verificações conforme ABNT NBR 5410 e demais normas aplicáveis, considerando dados reais da instalação.

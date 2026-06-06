Arquivo: index.html

O que está aqui
- index.html: página estática pronta para listar produtos e direcionar para pagamentos (MercadoPago, Stripe, Pix).

Tarefas antes de publicar
- Substitua os atributos `data-...` nos elementos `.card` pelos links/strings reais:
  - `data-mercadopago-url` → link de checkout do MercadoPago
  - `data-stripe-url` → link de checkout do Stripe
  - `data-pix-payload` → payload BRQ/Copia-e-cola do Pix
  - `data-download-url` → link do arquivo para download (use links assinados em produção)

Como criar um ZIP (Windows PowerShell)
```powershell
Compress-Archive -Path .\index.html -DestinationPath site.zip
# incluir assets se houver
Compress-Archive -Path .\assets -DestinationPath site-assets.zip
```

Como criar ZIP (Linux/macOS)
```bash
zip -r site.zip index.html assets/
```

Como enviar ao repositório Git
```bash
git init                # se ainda não inicializou
git add index.html README.md
git commit -m "Add site static" 
git remote add origin <url-do-seu-repo>
git branch -M main
git push -u origin main
```

Como subir ao UOL Host via FTP (exemplo)
- Conecte com FileZilla usando as credenciais FTP do painel UOL
- Envie `index.html` para a pasta `public_html` (ou `www`)

Observações de segurança
- Não coloque arquivos sensíveis ou downloads públicos sem proteção.
- Para vendas digitais, implemente links de download assinados no backend que validem pagamento.

Se quiser, posso:
- Gerar o ZIP aqui e instruir como baixar (preciso permissão para criar artefato de download),
- Ou conectar ao seu repositório e abrir um PR (forneça acesso ao repo).

Próximo passo sugerido: me diga se quer que eu gere o ZIP aqui no workspace para baixar.

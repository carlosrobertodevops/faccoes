Google Colab + Sheet + auth

Este erro ocorre quando as credenciais fornecidas não são nem do `oauth2client` nem do `google-auth`. Aqui está uma possível solução para o problema:

```python
from google.colab import auth
auth.authenticate_user()

import gspread
from google.auth import default

creds, _ = default()
gc = gspread.authorize(creds)
```

Neste código, a função `default()` do módulo `google.auth` é usada para obter as credenciais padrão¹. Em seguida, essas credenciais são passadas para a função `authorize()` do módulo `gspread` para autorizar o acesso às planilhas do Google¹.

Espero que isso ajude! Se você tiver mais perguntas, fique à vontade para perguntar.

Origem: conversa com o Bing, 09/04/2024
(1) python - TypeError: Credentials need to be from either oauth2client or .... https://stackoverflow.com/questions/71686960/typeerror-credentials-need-to-be-from-either-oauth2client-or-from-google-auth.
(2) oauth 2.0 - Automatic token fetching with OAuth2 client_credentials .... https://stackoverflow.com/questions/76736460/automatic-token-fetching-with-oauth2-client-credentials-flow-with-python-request.
(3) Credentials need to be from either oauth2client or from google-auth .... https://github.com/burnash/gspread/issues/1014.
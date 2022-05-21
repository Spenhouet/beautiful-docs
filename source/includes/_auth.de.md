# Authentifizierung

> Um sich zu authentifizieren, nutzen Sie diesen Code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Ersetzen Sie `meowmeowmeow` mit Ihrem API-Schlüssel.

Kittn verwendet API-Schlüssel um den Zugriff auf die API zu regeln. Sie können einen neuen Kittn API-Schlüssel auf unserem [Entwickler Portal](http://example.com/developers) erhalten.

Der API-Schlüssel muss bei jeder API-Anfrage im Header wie folgt mitgesendet werden:

`Authorization: meowmeowmeow`

<aside class="notice">
Ersetzen Sie <code>meowmeowmeow</code> mit Ihrem API-Schlüssel.
</aside>
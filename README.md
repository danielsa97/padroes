### Sugestões de padronização
- Utilizar metodologia GitFlow 
- Sempre Utilizar SoftDeletes em migratios(exceto tabela pivô).
- Sempre adicionar a chamada do pacote ao inicio da classe. \
 ERRADO: 
 ```
 \Log::error('')
 ```
 CORRETO:
 ```
	use \Log;
    [...]
	Log::error('');
```
- Em Request de formularios sempre adicionar os nomes dos attributos em ingles para portugues, afim de melhorar mensagens de erro.
```
	public function attributes(){
		return['password'=>'Senha', 'user'=>'Senha'];
	}
	
```

- Nome de diretórios(views, services) no singular, padronizar tambem a forma de escrita: \
ex: local-atendimento(), LocalAtendimento


- Inserir try catch em todos os metodos em services e usar throw new Exception para mensagens de erro

- Padronizar loading em requisições ajax(toda requisição deve ter loading)

- Sempre usar request Customizada(ate mesmo em requisições ajax) e criar regras de validação afim de evitar ataques

- Sempre adicionar dependencias no app.js(não adicionar diretamente na view blade) \
ex: 
    ```
    require('datepicker');
    ```

- Centralizar local de scripts 

- Centralizar CSS Global(usado em varios componentes) no diretório do SASS(não inserir diretamente nas views) e usar CSS especifico do componente em ESCOPO.
- Padronizar como JsonResponse(ou ResponseHttpException em caso de erros) todos os Controllers
- Utilizar codigos de retorno HTTP para definir status da requisição ao inves de usar o atributo "status".

Lista com significado dos codigos HTTP de retorno: https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status

    ERRADO:
       ```
       return response()->json([
          'status' => true,
          'message' => 'Usuário criado com sucesso' 
        ]);
	
	return response()->json([
          'status' => false,
          'message' => 'Usuário não encontrado' 
        ]);
        ```
    CORRETO:
    ```
    return response()->json(['message' => 'Usuário criado com sucesso'], 201);
    
    
    return response()->json(['message' => 'Usuário não encontrado'], 404);
    ```
- Toda id deve ser tipo UUID


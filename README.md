### Sugestões de padronização
- Sempre adicionar a chamada do pacote ao inicio da classe.
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
- Adicionar suporte v-model em componentes afim de padronizar entrada de dados

- Nome de diretórios(views, services) no singular, padronizar tambem a forma de escrita:
 ex: local-atendimento, LocalAtendimento, local_atendimento

- Se for trabalhar com parametrização, seguir padrão em captura de valores em switchers, bem como padronizar o que sera usado na hora de capturar o resultado selecionado pelo sistema(se vai ser a chave ou a descrição do parametro)
	ex: {1:'Sim',2:'Não'}

- Inserir try catch em todos os metodos em services e usar throw new Exception para mensagens de erro

- Padronizar loading em requisições ajax(toda requisição deve ter loading)

- Sempre usar request Customizada(ate mesmo em requisições ajax) e criar regras de validação afim de evitar ataques

- Sempre adicionar dependencias no app.js(não adicionar diretamente na view blade)
    ex: 
    ```
    require('datepicker');
    ```

- Centralizar local de scripts 

- Centralizar CSS no diretório do SASS(não inserir diretamente nas views)
- Padronizar como JsonResponse(ou ResponseHttpException em caso de erros) todos services que retornam dados para view
- Utilizar codigos de retorno para definir status da requisição.
    ERRADO:
       ```
       return [
          'status' => true,
          'message' => 'Sucesso' 
        ];
        ```
    CORRETO:
    ```
        return response()->json(['message' => 'Sucesso'], 200);
        ```


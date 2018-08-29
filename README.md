# eNotas GW PHP client
```php
eNotasGW::configure(array(
	'apiKey' => '<sua api key>'
));
```

### Emitindo uma nota fiscal
```php

$idEmpresa = '484FB0C5-969E-46AD-A047-8A0DB54667B4';

eNotasGW::$NFeApi->emitir($idEmpresa, array(
	'tipo' => 'NFS-e',
	'idExterno' => '5', //id para mapeamento com sistema de origem (opcional)
	'ambienteEmissao' => 'Homologacao', //'Homologacao' ou 'Producao'
	'cliente' => array(
		'nome' => 'Nome Cliente',
		'email' => 'cliente@mail.com',
		'cpfCnpj' => '23857396237',
		'tipoPessoa' => 'F',
		'endereco' => array(
			'uf' => 'MG', 
			'cidade' => 'Belo Horizonte',
			'logradouro' => 'Rua 01',
			'numero' => '112',
			'bairro' => 'Savassi',
			'cep' => '32323111'
		)
	),
	'servico' => array(
		'descricao' => 'Discriminação do serviço prestado'
	),
	'valorTotal' => 10.05
));
```

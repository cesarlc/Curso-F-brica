# desafio3_itflex

## Instalação e Execução:

> **Esse manual foi escrito para o Linux**

Para o funcionamento dessa aplicação siga os seguintes passos:

1) Instalar os seguintes pacotes:
* Python
* pip
* Django 1.8
* Sqlite
* djangorestframework (instalado via pip)
	
	OBS.: Recomenda-se o uso de virtualenv.

2) Baixar o projeto da plataforma Git: https://github.com/jota-info/desafio3_itflex.git
        
3) Copiar o diretório 'vagaitflex' (desafio3_itflex/vagaitflex) para a pasta raiz do Django

4) Abra o terminal, navegue e entre até o diretório 'vagaitflex'. E execute o seguinte comando:

  <code>$ python manage.py runserver</code>

5) A aplicação poderá ser visualizada e utilizada no navegador, através do acesso de:

  <code> localhost:8000/lista_tarefas/</code>
  
## Funcionamento e Testes:

1) Listar todas as tarefas:

* Curl: (certifique-se de que há tarefas cadastradas) 
<code>  curl -X GET http://localhost:8000/lista_tarefas/rest/tarefas/ </code>

* URL Navegador:<code>http://localhost:8000/lista_tarefas/</code>

2) Criar tarefa: (No campo status, o valor "0" significa não concluído, e o valor "1" significa concluído)

* Curl:
<code> curl -X POST -H "Content-Type: application/json" -d '{"titulo": "Exemplo_titulo", "descricao": "exemplo_descricao", "status":"0"}' http://localhost:8000/lista_tarefas/rest/adicionar_tarefa/
 </code>

* URL Navegador: <code> http://localhost:8000/lista_tarefas/adicionar_tarefa/ </code> ou clicar no link 'Nova tarefa' na página inicial.

3) Excluir tarefa:

* Curl: <code>curl -X DELETE http://localhost:8000/lista_tarefas/rest/excluir_tarefa/id_tarefa/ </code>

* URL Navegador: <code> http://localhost:8000/lista_tarefas/excluir_tarefa/id_tarefa</code>

4) Alterar Status da tarefa:

* Curl: (Status 0 = não concluído, Status 1 = concluído) <code> curl -X POST -H "Content-Type: application/json" -d '{"status":"0"}' http://localhost:8000/lista_tarefas/rest/alterar_status/id_tarefa/ </code>

* URL Navegador: <code> http://localhost:8000/lista_tarefas/alterar_tarefa/id_tarefa/ </code>

5) Alterar tarefa:

* URL Navegador: <code> http://localhost:8000/lista_tarefas/alterar_tarefa/id_da_tarefa/ </code>

## Logs das ações do sistema:

O Arquivo de Log das ações do sistema se encontra no diretório:

<code>desafio3_itflex/vagaitflex/lista_tarefas.log</code>

C:\Program Files\MongoDB\Server\4.0\bin>
mongo
mongoimport --db todot -c tasks --type csv --file tasks.csv --headerline
show dbs
use (todot)
show collections

-----Seleção:

db.tasks.findOne()
db.tasks.find()
db.tasks.find().pretty()
db.tasks.count()
db.tasks.limit()
db.tasks.limit().pretty()

db.tasks.find( {"titulo" : "Titulo C" } ).pretty()
db.tasks.find( {"titulo" : "Titulo H", "descricao" : "es6" } ).pretty()

-----Apresentação:

db.tasks.find({"descricao": /e/}).pretty() - Contém a letra 'e'
db.tasks.find({"descricao": /e$/}).pretty()  - Contém a letra 'e' no final da palavra
db.tasks.find({"descricao": /^e/}).pretty()  - Contém a letra 'e' no início da palavra


db.tasks.find().sort({_id:1}).limit(3).pretty() - Lista em ordem crescente (1)
db.tasks.find().sort({_id:-1}).limit(3).pretty() - Lista em ordem descrescente(-1)



-------Inserção: 

db.tasks.insert({"titulo":"Titulo Z", "descricao":"Top"}) - Inserir uma colletion
db.tasks.insertMany([{"titulo":"Titulo I"},{"descricao":"Será?"}]) - Inserir várias collections


-------Atualização:
db.tasks.update({"titulo":"Titulo A"},{"descricao":"MongoDB"}) - Atualiza o objeto inteiro
db.tasks.update({"titulo":"Titulo A"},{$set:{"descricao":"MongoDB"}}) - Atualiza somente a chave
db.tasks.update({},{$set:{"descricao":"MongoDB"}}) - Atualiza todos os objetos e se não houver essa chave , cria-se

-------Exclusão:

db.tasks.remove({"titulo":"Roracle"}) - Remove todos os objetos com essa condição
db.tasks.update({},{$unset:{"descricao":"MongoDB"}}) - Remove de todos os objetos uma chave , cria-se

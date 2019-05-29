mongo
mongoimport --db todot -c tasks --type csv --file tasks.csv --headerline
show dbs
usw (todot)
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



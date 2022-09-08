## Instalando os pacotes:
npm install

## Iniciando servidor:
npm run dev

# CONFIGURAÇÃO DO PRISMA - CRIANDO 
- bibliothecas necessarias: 

"@prisma/client": "^4.2.1",
"prisma": "^4.2.1",


commando cmd: npx prisma init

vai solicitar um nome: pode colocar o que preferir;

Esse projeto cria toda a parte do banco, onde configuramos:
Tipo de Banco: postgresql
Local , Porta e senha no arquivo .env
colocar as credencias do seu Banco


# CONFIGURAÇÃO DO PRISMA - BANCO JÁ EXISTENTE

- bibliothecas necessarias: 

"@prisma/client": "^4.2.1",
"prisma": "^4.2.1",

 commando cmd: npx prisma init

- Conectar um banco existente e integra-lo ao seu projeto 

 definer NO ARQUIVO .ENV:  
 DATABASE_URL="nome_banco://usuario:senha@local_banco:porta/nome_do_banco_que_possui_as_tabelas"

 banco: user + password + local_banco_de_dados / port / qual_banco_quero

- Archive: schema.prisma definir o banco: 

generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "seu banco"
  url      = env("DATABASE_URL")
}

- Commando cmd: npx prisma db pull

sera adicionado todo o esquema do banco existente no seu projeto arquivo: prisma/schema.prisma
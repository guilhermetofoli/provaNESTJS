COMANDOS BÁSICOS PROVA NEST

#Link baixar NodeJS
https://nodejs.org/pt-br/download

#Comando para iniciar estrutura em nest
npm i -g @nestjs/cli

#Começar novo nest
nest new <nome_do_projeto>

#Selecione a opção “npm”

#Executar aplicação em nest
npm run start

COMANDOS CRIAR COMPONENTES

	#Significado de cada etapa
●	nest generate service <nome_do_serviço>
				
				#No Terminal
				nest g s <nome_do_serviço>

BIBLIOTECA SEQUELIZE (INSTALAÇÃO)

Com o sequelize é possível que o “model" interaja com o banco de dados

#Instalação do Sequelize
npm i --save @nestjs/sequelize sequelize sequelize-typescript mysql2
npm i --save-dev @types/sequelize

npm i --save @nestjs/config
#Instalar para conmexão com o BD:

npm install @nestjs/typeorm typeorm mysql2

#Após a instalação importe os seguintes módulos no “app.module.ts”

import { SequelizeModule } from '@nestjs/sequelize';
import { ConfigModule } from '@nestjs/config';

#Altere o imports dentro de @module para:
imports: [ConfigModule.forRoot()],

#Validar configurações
nest start

#Vá para o browser e busque localhost:3000

COMANDOS BASE PARA CRIAR ARQUIVOS REFERENTES A CLASSES

UTILIZANDO CLASSE LIVRO COMO EXEMPLO

#Comando
nest g resource livros

✔ What transport layer do you use? REST API
✔ Would you like to generate CRUD entry points? Yes


1 - CRIAR O MODEL (Entidade)
●	Crie o arquivo livro.model.ts manualmente.
●	Defina a classe com @Table e @Column.
●	É aqui que você olha o Diagrama de Classes para criar os campos (titulo, autor, etc).

2 - CRIAR O MODULE (Configuração)
#No terminal: 
nest g module livro

●	Ação: Importe o SequelizeModule.forFeature([Livro]) no array de imports.
●	Por que: Isso "conecta" o Model ao banco de dados dentro do Nest.
 

3 — CRIAR O SERVICE (Lógica/Funções)

#No terminal: 
nest g s livro

●	Ação: No constructor, use o @InjectModel(Livro).
●	Crie os métodos: create(), findAll(), findOne() e destroy().

4 — CRIAR O CONTROLLER (Rotas/Endpoints)

#No terminal: 
nest g co livro

●	Ação: No constructor, injete o LivroService.
●	Crie os métodos com @Post(), @Get(), @Delete() chamando o Service.
 

Link repo

https://github.com/Anderson-Iwazaki/exemplo_nest_unicesumar.git

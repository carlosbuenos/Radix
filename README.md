É uma API feita em asp.net core 2.1.
Utiliza swagger .
Injeção de dependencia nativa .
Para levantar a api é só efetuar o pull do container, após a conclusão do dowload deve-se executar o seguinte comenado no prompt.

docker run -p 7000:7000 cbuenohub/radix:latest

verifique seu ip e digite [Seu IP]:7000/swagger

peço antecipadamente desculpas pela pobreza da aplicação pois eu criei apenas um método de input de eventos e um método de output. o output é cumulativo e agrupado por tags e só retorna caso o valor seja numérico.
mas não foi criado um front com gráficos nem funções que permitam filtrar os dados por hora por exemplo.
não foi criada uma base temporária, a aplicação está conectada a uma base sqlserver na nuvem e nesta base existe uma Tabela chamada Eventos o script de criação está logo abaixo.

CREATE TABLE [dbo].Eventos NOT NULL,
[TimeStamp] [bigint] NOT NULL,
[Valor] varchar NULL,
CONSTRAINT [PK_Eventos] PRIMARY KEY CLUSTERED
(
[TimeStamp] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]

Crie tags e atribua valores a coluna timestamp é atribuída em tempo de execução não havendo necessidade de preencher valor para testar como por exemplo o json abaixo.

{
"tag": "BUENO.TESTE.NET",
"timeStamp": 0,
"valor": "123"
}

os fontes estão no meu repositório no bitbucket
https://bitbucket.org/_Cbueno/radix/

peço que não criem novas tabelas na base pois ela é uma base emprestada por um amigo.
(sei não fariam isso mas prefiro pedir do que deixar subentendido).
desde já agradeço pela oportunidade

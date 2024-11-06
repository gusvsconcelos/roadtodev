# **Web Service SOAP em Python**

Para implementar um Web Service SOAP, são utilizados frameworks como Django e Spyne, que simplificam a criação e disponibilização de serviços. A estrutura de uma aplicação SOAP envolve a definição do servidor, o WSDL e a comunicação usando XML.

## Estrutura da Aplicação

- ==A aplicação é hospedada em Django, com **Spyne** responsável pela criação do Web Service.==
- São necessários os pacotes `spyne` e `lxml` para transformar dados XML e gerar o WSDL automaticamente.

## Configuração do Servidor SOAP

- Criação de um repositório de dados com temas e módulos.
- Definição dos serviços no Django com o Spyne, criando métodos para listar temas (`getTemas`) e módulos específicos (`getModulosTema`).

### *Cliente SOAP*
A biblioteca `zeep` permite criar clientes para consumir Web Services SOAP em Python. O cliente é configurado para acessar o WSDL e invocar métodos no servidor, facilitando a integração com o Web Service.
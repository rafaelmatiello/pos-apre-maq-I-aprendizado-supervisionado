# Aprendizado de máquina 1: Aprendizado supervisionado
 - Professor: Marco Beber, MSc
 - marco.beber@hotmail.com
 
 Links:
 - https://www.kaggle.com/

# Tipo de aprendizado


	- Aprendizado supervisionado
		- Os exemplos, tem atributos com 
		- classificação
		- tem uma classe para guiar
	- Não supervisionado
		- não tem um guia,
		- agrupar os exemplos por quanto parecidos eles são
	- Reforço
	
# Forma de classificação e regressão

	- Regressão
	
	- Classificação binária
		- Resultado sim ou não.
		- Span, sim ou não?
		- fraude? sim ou não?
	- Multi classe 
		- Categorização de plantas, animais
		- Reconhecimento de digitos, tem uma imagem com um digito, verificar qual é mais próximas de 0-9
		- mais de uma categoria, e precisa classificar qual é a categoria.
	- Multi label
		- Vai escolher mais de uma classe relacionada.
		- Categorização de noticia.
			- Varias tags, como Politica e Saúde
		- Detecção de objetos
			- quanto tiver mais um objeto na imagem.

# Paradigmas de aprendizado
	- Aprendizagem estatística
		- Define uma linha e projeta os próximos, a partir de uma função
	- Simbolica
		- Arvore de decisão, 
		- exemplo do jogar tenis, considerando vento (Fraco? forte?), clima(Ensolarado? chuvosso? Nublado?), umidade( Sim ou Não?)...
	- Baseada em instâncias
		- Olhando os vizinhos, ele vai ser igual aos vizinhos mais próximos. (KNN)
		- definir uma função em relação aos tipos.

# Crisp-dm
	- Processo para analise de dados.
	- pode ser continuo ou inicial e final.
	- problema -> entendimento dos dados -> preparação dos dados -> modelo -> avaliar resultado...
	- business Undestanding: 

# limpeza dos dados
	- Conhecimento de dominio
		- saber o intervalor
	- utilizar estatística
		- remover out layer.
	- Normalização de dados númericos
		- km, metros, horas, segundos
	- Linear
		- manter os dados em 0 e 1
	- máximo
		- entre -1 e 1
	- z-score
		- unidades de desvio padrão em relação a media.
		- quantos desvio distante da média
		- distribuição normal (

# Descritização dos dados
	- Ao invés de usar cm de altura, transformar para categorias, alto, baixo, baixo.
	- Mapeamento direto
		- troca número por categórico
		- 1 - Ruim
		- 2 - Bom
		- 3 - Otimo
	- Mapeamento por intervalos.
		- pré-definidos
			- definir faixa conforme o negócio
			- exemplo:
			- até 12 anos - criança
			- 12 a 18 anos - adolecsente
			- 18 a 40 anos - adulto
		- mesmo tamanho
			- Tem que saber o máximo e o mínimo, divide por k partições.
			- 100 em 4 partições, 0 - 25, 26-50....
			- poderia mais valores em um bloco e menos em outros.
			- número diferentes por partição
		- mesma frequencia
			- mesmo quantidade por intervalo
			- mesmo número de exemplos por partição.

# tranformação de dados qualitativo ou categóricos
	- Ordinais: ruim, regular, bom, ótimo
	- Nominais: genero, estado civil, (não tem sequencia lógica)
	- mapeamento direto
		- cuidar sobre qual o algoritmo usar, para um não ser x vezes o outro
		- exemplo, cuidar, não faz sentido
			- solteiro - 0
			- casado - 1
			- viúvo - 2
			- divorciado - 3
		- exemplo, faz sentido, porque um é x vezes mais o que o outro
			- ruim - 1 
			- bom - 2 
			- ótimo - 3
	- one-hot
		- transformar o valor em uma nova catégoria
		- fazer um binario, com as opções
		- solteiro(0,1), casado(0,1).... todas são 0 exeto para o solteiro.

# outras transformações
	- extrais campos data, pode extrair mais informações.
		- anos 19/02/2020
		- idade		dia		mes		anos
			1		19		2		2020
	- Cruzamento de variáveis
		- salário x idade
	
# tratamento de dados núlos
	- ignorar valor desconhecidos, ignorar se for poucos, em uma quantidade grande.
	- até 5% de dados nulos, corta a variável, mas as vezes é relevando verifcar caso a caso.
	- valor constante, representar com um dado faltante, exemplo: média, moda e mediana, e mais uma variável para informar que o dado foi alterado.
	- colocar na instancia mais semelhante. KNN
	- em uma normal, pode usar a média para completar, se não é normal, pode completar com o KNN, mas tem experimentar, unilateral, pode colcar a moda ou a mediana;
	- pode verificar se tem colação com a veriável dependente que quer prediser, 
	
# Método de amostragem
	- Resustituição
		- criar e testar 
		- reserva uma parte para treino
			- indutor (modelo)
			- calcular o resultado.
		
	- Holout
		- 70 treino, 30 para teste.
		- Usos:
			- Pode rodas em mais de uma vez, mudando o 70-30 para validar.
			- Pode trabalhar com intervalo de confiaça;
		- treino -> modelo -> resultado -> compara o resultado com o modelo que ficou
		- grande volume de dados
	- Cross  validation
		- Consegue validar o usando o dataset inteiro, poucos dados
		- Se tiver um resultado constante entre todas as partições, pode ser um algoritmo mais estavél
		- Definir as pertições entre 5 ou 10.
		- 5 -> k -1 = 4 para testes 1 para validar.
			- repetir por para cada bloco, mudando que é o treino e quem validar
			1-4 treino valida 5, 1,3,4,5 -> valida 2...
		- 10 -> k -1 = 9, para testes 9 teste 
		- Custo computacial é muito grande, se tiver muito volume de dados pode não utilizar.
		- volume pequeno de dados.
	- Qual eu uso
		- Teste de hipotese, para verificar qual é o melhor para utilizar.
		- Qual utilizar?
		
# aulas 2
	- Fit
		-  vai aprender com base nos dados
		- transforme
	- Transform 
		- teste
	- Graficos com mais montanhas são ruins
		- bin modal, duas 
		- Encontrar alguma lógica para ver porque sobe e desce.
		- criar um subspace para trabalhar com os dados.
	- OnHotencoder
		- tranforma a categoria em variável
		- criar o esquema de colunas com 0, 1
		- qualitativa
	- MinMaxScaler
		- exemplo: idade para um scala de 0 a 1 
		- assim todas as features vão ficar na mesma escala. de 0 a 4
			- 0 -0
			- 1 - 0,25
			- 2 - 0,5
			- 3 - 0,75
			- 4 - 1
		- quantitativa
	- kfold
		- separa os dados em x (5) partes
		- shuffle - > randominar os dados.
		- uma partição é utilizada para o teste
		- 1 é treinio, 0 é teste
	- viés
		- alto valor de erro
		- a linha por exemplo, não consegue aproxinal de forma adequando o modelo real que é um curva
	- variancia
		- 
		
selling_price

	
	
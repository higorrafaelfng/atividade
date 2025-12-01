import pandas as pd
import random

def criar_dado_float_aleatorio_com_nome(nome):
    """
    Cria um DataFrame do Pandas com um nome e um número float aleatório 
    entre 0.0 e 1.0 (exclusivo de 1.0).
    """
    # 1. Gera um número float aleatório entre 0.0 e 1.0
    valor_aleatorio = random.random() # Gera um float X, onde 0.0 <= X < 1.0
    
    # 2. Podemos multiplicar para ter um range mais útil, por exemplo, de 0.0 a 10.0
    valor_formatado = round(valor_aleatorio * 10, 4) # Arredonda para 4 casas decimais
    
    # 3. Cria um dicionário com os dados
    dados = {
        'Nome': [nome],
        'Nota de Desempenho (0.0 a 10.0)': [valor_formatado]
    }
    
    # 4. Cria o DataFrame do Pandas
    df_aleatorio = pd.DataFrame(dados)
    
    return df_aleatorio

# Define o nome
nome_pessoa = "Higor"

# Cria o DataFrame com o novo valor aleatório (float)
df_resultado_float = criar_dado_float_aleatorio_com_nome(nome_pessoa)

# Exibe o resultado
print(f"*Novo Resultado Aleatório para o nome '{nome_pessoa}':*")
print(df_resultado_float)

# Exemplo de como acessar o valor float gerado:
nota = df_resultado_float['Nota de Desempenho (0.0 a 10.0)'].iloc[0]
print(f"\nO valor float aleatório gerado para {nome_pessoa} é: {nota}")

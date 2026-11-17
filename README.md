Script para criar o arquivo Python
corrigido e formatado
code_content = '''import matplotlib.pyplot as plt from collections import Counter
Classe para representar um livro
class Livro: def init(self, titulo, autor, ano_publicado): self.titulo = titulo self.autor =
autor self.ano_publicacao = ano_publicado
def __str__(self):
 return f"'{self.titulo}' por {self.autor}, publicado em
{self.ano_publicacao}"
Lista para armazenar a biblioteca de
livros
biblioteca = []
Função para adicionar um livro à
biblioteca
def adicionar_livro(titulo, autor, ano_publicacao): novo_livro = Livro(titulo, autor,
ano_publicacao) biblioteca.append(novo_livro) print(f"'{titulo}' foi adicionado à
biblioteca.")
Função para listar todos os livros na
biblioteca
def listar_livros(): print("\n--- Livros na Biblioteca ---") if not biblioteca: print("Nenhum
livro cadastrado.") for livro in biblioteca: print(livro) print("----------------------------\n")
Adicionando alguns livros à biblioteca
adicionar_livro("Livro 1", "Autor 1", 1605) adicionar_livro("Livro 2", "Autor 2", 1813)
adicionar_livro("Livro 3", "Autor 3", 1949) adicionar_livro("Livro 4", "Autor 4", 1967)
adicionar_livro("Livro 5", "Autor 5", 1951)
Listar todos os livros cadastrados
listar_livros()
--- Gerar gráfico de distribuição por
ano ---
Extrair todos os anos de publicação da
biblioteca
todos_os_anos = [livro.ano_publicacao for livro in biblioteca]
Obter os anos únicos e ordená-los
para o eixo X
anos = sorted(list(set(todos_os_anos)))
Contar a frequência de cada ano na
lista completa
contagem_anos_dict = Counter(todos_os_anos)
Criar a lista de contagens na mesma
ordem dos anos
contagem_por_ano = [contagem_anos_dict[ano] for ano in anos]
Criar o gráfico de linha
plt.figure(figsize=(8, 5)) plt.plot(anos, contagem_por_ano, marker='o', linestyle='-',
color='b') plt.xlabel('Ano de Publicação') plt.ylabel('Número de Livros')
plt.title('Distribuição de Livros na Biblioteca por Ano de Publicação')
Adicionar rótulos aos pontos de dados
for i, valor in enumerate(contagem_por_ano): plt.text(anos[i], valor, str(valor),
ha='center', va='bottom')
plt.grid(True) plt.tight_layout() plt.show() '''
file_path = "sistema_biblioteca.py" with open(file_path, "w", encoding="utf-8") as f:
f.write(code_content)
print(f"Arquivo salvo com sucesso em: {file_path}")

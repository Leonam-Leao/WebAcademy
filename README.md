# WebAcademy

classDiagram
    class Aluno {
        -String cpf
        -String senha
        -String nome
        -String matricula
        +fazerLogin()
        +visualizarPerfil()
    }

    class Disciplina {
        -String idDisciplina
        -String nome
        -int progressoAula
        -double nota
        +atualizarProgresso()
    }

    class RestauranteUniversitario {
        -double saldoCarteira
        -String statusRefeicao
        +consultarCardapio()
        +recarregarSaldo()
    }

    class Cardapio {
        -Date data
        -String pratoPrincipal
        -String guarnicao
        -String suco
    }

    class Documento {
        -String idDocumento
        -String tipoDocumento
        -String statusEmissao
        +solicitarDocumento()
        +fazerDownload()
    }

    class BibliotecaVirtual {
        -int progressoLeitura
        +buscarLivro()
        +consultarHistorico()
    }

    class Livro {
        -String idLivro
        -String titulo
        -String autor
    }

    class Noticia {
        -String idNoticia
        -String titulo
        -String conteudo
        -Date dataPublicacao
    }

    class Pagamento {
        -String idPagamento
        -double valorTotal
        -String formaPagamento
        +gerarPix()
        +gerarCartao()
    }

    %% Relacionamentos
    Aluno "1" --> "1" RestauranteUniversitario : possui
    RestauranteUniversitario "1" --> "*" Cardapio : exibe
    RestauranteUniversitario "1" --> "*" Pagamento : realiza
    Aluno "1" --> "*" Disciplina : cursa
    Aluno "1" --> "*" Documento : solicita
    Aluno "1" --> "1" BibliotecaVirtual : acessa
    BibliotecaVirtual "1" --> "*" Livro : contem
    Aluno "1" --> "*" Noticia : visualiza

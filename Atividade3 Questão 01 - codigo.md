# Atividade03 - POO
Repositório destinado a atividade de POO - Atividade 3 

Questão 01 

package questoes;
import java.util.Date;

abstract class BasePessoa {
    protected int codigo;
    protected String nome;
    protected String endereco;
    protected String telefone;
    protected Date dataNascimento;
    protected String rg;
    protected Date dataInsercao;

    public BasePessoa(int codigo, String nome, String endereco, String telefone, Date dataNascimento, String rg, Date dataInsercao) {
        this.codigo = codigo;
        this.nome = nome;
        this.endereco = endereco;
        this.telefone = telefone;
        this.dataNascimento = dataNascimento;
        this.rg = rg;
        this.dataInsercao = dataInsercao;
    }
}

class Professor extends BasePessoa {
    String registro;
    Date dataContratacao;

    public Professor(int codigo, String nome, String endereco, String telefone, Date dataNascimento, String rg, Date dataInsercao,
                     String registro, Date dataContratacao) {
        super(codigo, nome, endereco, telefone, dataNascimento, rg, dataInsercao);
        this.registro = registro;
        this.dataContratacao = dataContratacao;
    }
}

class Aluno extends BasePessoa {
    String matricula;
    Date dataMatricula;

    public Aluno(int codigo, String nome, String endereco, String telefone, Date dataNascimento, String rg, Date dataInsercao,
                 String matricula, Date dataMatricula) {
        super(codigo, nome, endereco, telefone, dataNascimento, rg, dataInsercao);
        this.matricula = matricula;
        this.dataMatricula = dataMatricula;
    }
}

public class Main {
    public static void main(String[] args) {
        Date dataHoje = new Date();

        Professor professor = new Professor(1, "Luizão", "Rua Owaldo Cruz", "12375490837", new Date(80, 4, 15), "1234567", dataHoje, "123634076", new Date(120, 0, 10));
        Aluno aluno = new Aluno(2, "Hiury Marçal", "Rua Generoso Leite Nº 819 - Vila Marli", "987654321", new Date(95, 7, 25), "9876543", dataHoje, "0987", new Date(123, 2, 20));

        System.out.println("Professor:");
        System.out.println("Nome: " + professor.nome);
        System.out.println("CPF: " + professor.registro);
        System.out.println("Data de Contratação: " + professor.dataContratacao);
        System.out.println("\nAluno:");
        System.out.println("Nome: " + aluno.nome);
        System.out.println("Matrícula: " + aluno.matricula);
        System.out.println("Endereço: " + aluno.endereco);      
        System.out.println("CPF: " + aluno.rg); 
        System.out.println("Data de Matrícula: " + aluno.dataMatricula);
    }
}

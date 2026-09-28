# ==============================================================================
# PROVA PRÁTICA AV2 - 3º BIMESTRE
# ARQUIVO: av2_sistema_modular.py
# Nome do Aluno:
# Data:
# Link do Repositório:
# ==============================================================================

dados_brutos = [
    "  carlos eduardo silva;desenvolvedor;11988887777  ",
    "  ana paula mendes;analista de rh;21977776666  ",
    "  roberto carlos oliveira;gerente de projetos;31966665555  "
]


def limpar_e_formatar_texto(texto):
    texto = texto.strip()
    texto = texto.upper()
    return texto


def extrair_codigo_ou_ddd(dado):
    dado = dado.strip()
    ddd = dado[0:2]
    return ddd


def processar_e_exibir_cadastros(lista_dados):
    total = 0

    for dado in lista_dados:
        partes = dado.strip().split(";")

        nome = limpar_e_formatar_texto(partes[0])
        cargo = limpar_e_formatar_texto(partes[1])
        telefone = partes[2].strip()
        ddd = extrair_codigo_ou_ddd(telefone)

        print(f"Nome: {nome}")
        print(f"Cargo: {cargo}")
        print(f"DDD: {ddd}")
        print(f"Telefone: {telefone}")
        print("-" * 50)

        total += 1

    return total


def main():
    print("==================================================")
    print("     SISTEMA DE GESTÃO MODULARIZADO - AV2        ")
    print("==================================================\n")

    print("Iniciando o processamento dos dados...\n")

    total_processado = processar_e_exibir_cadastros(dados_brutos)

    print(f"Total de registros processados: {total_processado}")

    print("\n==================================================")
    print("             PROCESSAMENTO CONCLUÍDO              ")
    print("==================================================")


if __name__ == "__main__":
    main()

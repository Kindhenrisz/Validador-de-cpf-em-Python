# Validador-de-cpf-em-Python
Aqui está um código em python que valida cpf.


# Validar CPF.
cpf = input('Digite o CPF sem pontos e sem digitos.')
#validação da string digitada se é número e certifica que consta 11 digitos do CPF
# usando a função len
if cpf.isnumeric() and len(cpf) == 11:
# declara variável lista.
    lista_cpf = []
    #separa cada número do cpf criando uma lista com base na string CPF
    for n_cpf in cpf:
    #append adiciona cada elemento dentro da lista com base na string CPF e transforma a string em int.
        lista_cpf.append(int(n_cpf))
        # print(f'controle da Validação{len(lista_cpf)}') Verificação de controle de código;
        # print(f'{lista_cpf}lista criada com o cpf digitado e alteradopara int') Verificação de controle de código;
        
        
        # Calculo da validação CPF.
    L_calc_1 = lista_cpf[:-2] # retira os dois ultimos digitos do cpf.
        # print(f'{L_calc_1}') Verificação de controle de código;
        
        #laço for para calculo de cada int
    cont_1 = 11
    mult_calc1 = []
    for n_mult in L_calc_1:
        cont_1 -= 1
            # print(f'{cont_1}') Verificação de controle de código;
        Valor_calc1 = n_mult*cont_1 # calculo da multiplicação inicia em 10.
        mult_calc1.append(int(Valor_calc1))
            
    Soma_Calculo1 = 0
    for soma in mult_calc1:
        Soma_Calculo1 += soma
    modulo_calc1 = 11-(Soma_Calculo1%11)
    
    if modulo_calc1 > 9:
        Primeiro_Digito = 0
    else:
        Primeiro_Digito = modulo_calc1
            
    L_calc_1.append(Primeiro_Digito)

            
    cont_2 = 12
    mult_calc2 = []   
    for n_calc2 in L_calc_1:
        cont_2 -= 1
        Valor_calc2 = n_calc2* cont_2
        mult_calc2.append(int(Valor_calc2))
                
    Soma_Calculo2 = 0
    for n_soma2 in mult_calc2:
        Soma_Calculo2 += n_soma2
    
    modulo_calc2 = 11-(Soma_Calculo2%11)
            
    if modulo_calc2 > 9:
        Segundo_digito = 0
    else:
        Segundo_digito = modulo_calc2
                
    L_calc_1.append(Segundo_digito)
        
    novo_cpf = L_calc_1
            
    if novo_cpf == lista_cpf:
        print(f"O CPF {cpf} é válido")
    else:
        print(f"O CPF {cpf} é inválido")             
else: 
    print("Por favor digite 11(onze) números sendo apenas números do cpf\
        sem pontos ou digitos.")
                
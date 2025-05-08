n = 10 
fatorial = 1

angulo = float(input("Digite o ângulo em radianos: "))
operacao = input("Escolha a operação (seno, cosseno, tangente, soma, subtração, multiplicação, divisão): ")

seno = 0
cosseno = 0
resultado = None

for i in range(n):
    termo_seno = ((-1) * i) * (angulo * (2 * i + 1))
    fatorial *= (2 * i + 1) * (2 * i) if i > 0 else 1  
    seno += termo_seno / fatorial

fatorial = 1
for i in range(n):
    termo_cosseno = ((-1) * i) * (angulo * (2 * i))
    fatorial *= (2 * i) * (2 * i - 1) if i > 0 else 1  
    cosseno += termo_cosseno / fatorial

if cosseno != 0:
    tangente = seno / cosseno
else:
    tangente = "Indefinido"

if operacao == "soma":
    num1 = float(input("Digite o primeiro número: "))
    num2 = float(input("Digite o segundo número: "))
    resultado = num1 + num2
elif operacao == "subtração":
    num1 = float(input("Digite o primeiro número: "))
    num2 = float(input("Digite o segundo número: "))
    resultado = num1 - num2
elif operacao == "multiplicação":
    num1 = float(input("Digite o primeiro número: "))
    num2 = float(input("Digite o segundo número: "))
    resultado = num1 * num2
elif operacao == "divisão":
    num1 = float(input("Digite o primeiro número: "))
    num2 = float(input("Digite o segundo número: "))
    if num2 != 0:
        resultado = num1 / num2
    else:
        resultado = "Indefinido"
elif operacao == "seno":
    resultado = seno
elif operacao == "cosseno":
    resultado = cosseno
elif operacao == "tangente":
    resultado = tangente
else:
    resultado = "Operação inválida"

print("Resultado:", resultado)

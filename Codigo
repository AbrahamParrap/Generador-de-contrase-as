#generador de contraseñas
import re
import secrets
import string

def generar_contraseña(longitud, nums, caracteres_especiales, mayusculas, minusculas):
    # Define los posibles caracteres para la contraseña
    letras = string.ascii_letters
    digitos = string.digits
    simbolos = string.punctuation

    # Combina todos los caracteres
    todos_los_caracteres = letras + digitos + simbolos

    while True:
        contraseña = ''
        # Genera la contraseña
        for _ in range(longitud):
            contraseña += secrets.choice(todos_los_caracteres)

        restricciones = [
            (nums, r'\d'),
            (minusculas, r'[a-z]'),
            (mayusculas, r'[A-Z]'),
            (caracteres_especiales, fr'[{simbolos}]')
        ]

        # Verifica las restricciones
        count = 0
        for restriccion, patron in restricciones:
            if restriccion <= len(re.findall(patron, contraseña)):
                count += 1

        if count == 4:
            break

    return contraseña

nueva_contraseña = generar_contraseña(8, 2, 2, 2, 2)
print(nueva_contraseña)

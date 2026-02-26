Validación de Registro de Productos: 
def registrar_categoria():
    nombre = input("Ingrese el nombre de la categoria: ")
    
    nombre = nombre.strip()
    
    if 5 <= len(nombre) <= 12:
        nombre_mayus = nombre.upper()
        print(f"Categoria registrada exitosamente: {nombre_mayus}")
    else:
        print("Error: el nombre ingresado no es valido. Debe tener entre 5 y 12 caracteres")

registrar_categoria()

Limpieza de Reseñas de Libros: 
def procesar_opinion():
    opinion = input("Ingresa tu opinion sobre el libro: ")
    
    opinion_limpia = opinion.strip( )
    opinion_limpia = opinion_limpia.lower( )
    cantidad_recomiendo = opinion_limpia.count("recomiendo")
    
    print("\n--- Resultado del Procesamiento ---")
    print("Opinion limpia:")
    print(opinion_limpia)
    print(f"\nLa palabra 'recomiendo' aparece {cantidad_recomiendo} veces.")

procesar_opinion()

Generador de Códigos ISBN y Seguridad: 
def validar_codigo_isbn(codigo):
    
    prefijo_oficial = "LIB-"

    
    if not codigo.startswith(prefijo_oficial):
        print("Prefijo incorrecto. Corrigiendo automaticamente")
        
        
        if "-" in codigo:
            codigo = codigo.split("-", 1)[1]
        
        
        codigo = prefijo_oficial + codigo

    
    parte_codigo = codigo[len(prefijo_oficial):]

    
    if len(parte_codigo) == 10 or len(parte_codigo) == 13:
        print("\n✅ Codigo valido dentro del sistema")
        return codigo
    else:
        print("\n❌ Código invalido")
        print("La parte del codigo debe tener 10 o 13 caracteres.")
        return None

codigo_usuario = input("Ingrese el codigo del libro: ")

resultado = validar_codigo_isbn(codigo_usuario)

if resultado:
    print("Codigo final almacenado:", resultado)
else:
    print("No se pudo registrar el libro.")

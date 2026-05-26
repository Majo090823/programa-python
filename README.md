# programa-python
Solución del Problema 3 del curso Fundamentos de Programación (213022) – UNAD. Auditoría de inventario en Python: matriz de artículos, función de cálculo de reabastecimiento y reporte de pedidos.
# Problema 3: Auditoría de Inventario
# Curso: Fundamentos de Programación
# 1. Matriz de inventario (al menos 5 artículos)
# Formato: [Código, Nombre, Stock Actual, Stock Mínimo]
inventario = [
    ["A001", "Tornillo", 150, 200],
    ["A002", "Tuerca", 30, 50],
    ["A003", "Arandela", 120, 100],
    ["A004", "Resorte", 5, 20],
    ["A005", "Cable USB", 2, 15]
]
# 2. Función para calcular la cantidad a pedir
def calcular_pedido(stock_actual, stock_minimo):
    """
    Retorna la cantidad exacta a pedir según la lógica:
    - Si el stock actual es menor al mínimo: pedir la diferencia.
    - Si es suficiente (>= mínimo): no pedir (0).
    """
    if stock_actual < stock_minimo:
        return stock_minimo - stock_actual
    else:
        return 0
# 3. Procesar el inventario y mostrar resultados
print("=" * 50)
print(" AUDITORÍA DE INVENTARIO - LISTA DE PEDIDOS ")
print("=" * 50)
# Recorremos cada artículo en la matriz
for articulo in inventario:
    # Extraemos los valores de la fila (desempaquetado)
    codigo = articulo[0]
    nombre = articulo[1]
    stock_actual = articulo[2]
    stock_minimo = articulo[3]
    # Llamamos a la función para obtener la cantidad a pedir
    cantidad = calcular_pedido(stock_actual, stock_minimo)
    # Solo mostramos los artículos que necesitan reabastecimiento
    if cantidad > 0:
        # Mensaje formateado con código y nombre
        print(f" {codigo} - {nombre}: Pedir {cantidad} unidades")
print("=" * 50)

# Quiz Semana 2 - Empresas

## ¿Qué hice?

De acuerdo con la base que el profesor nos entregó, inicié a desarrollar cada una de las partes marcadas como `TODO` dentro del código. A continuación explico paso a paso lo que fui completando en cada sección.

### 1. Constructor de la clase Empresa (`__init__`)

Dentro del constructor guardé cada dato recibido como un atributo del objeto usando `self`. Para `num_empleados` e `ingresos_anuales` los convertí con `int()`, ya que al leerlos desde el archivo `.txt` llegan como texto (string) y no se pueden usar en operaciones matemáticas si no se convierten primero.

### 2. Método obtener_informacion()

Completé el `return` con un f-string que arma un texto legible mostrando el nombre, sector, número de empleados e ingresos de la empresa, por ejemplo:
`TechNova | TECNOLOGIA | 150 empleados | $500000000`

### 3. Función leer_empresas()

Agregué la validación solicitada: por cada línea del archivo, si `num_empleados` es mayor a 0, se crea un objeto `Empresa` con esos datos y se agrega a la lista `empresas`. Si es 0 o negativo, la línea se ignora (por eso `EmpresaFantasma`, que tiene -5 empleados, no aparece en los resultados finales).

### 4. Función calcular_total_ingresos()

Recorrí la lista de empresas con un `for` y fui sumando el atributo `ingresos_anuales` de cada una en una variable `total`, que al final se retorna.

### 5. Función filtrar_por_sector()

Creé una lista vacía y recorrí todas las empresas comparando su atributo `sector` con el sector recibido como parámetro. Si coinciden, la empresa se agrega a esa nueva lista, que es la que se retorna al final.

### 6. Función empresa_con_mas_empleados()

Primero valido que la lista no esté vacía (si lo está, retorno `None`). Luego tomo la primera empresa como punto de partida y voy comparando: si encuentro una con más empleados, la guardo como la nueva "mejor". Al final del recorrido queda la empresa con más empleados.

### 7. Función promedio_empleados()

Sumé el número de empleados de todas las empresas y dividí ese total entre la cantidad de empresas en la lista. También validé que si la lista está vacía, se retorne 0 para evitar un error de división entre cero.

## Cómo ejecutar el programa

1. Abrir la carpeta del proyecto en Visual Studio Code.
2. Abrir una terminal (Terminal > New Terminal).
3. Asegurarse de estar dentro de la carpeta del proyecto.
4. Ejecutar el comando:

5. El programa lee automáticamente el archivo `empresas.txt` y muestra en consola:
   - Todas las empresas registradas (válidas)
   - El total de ingresos
   - Las empresas del sector TECNOLOGIA
   - La empresa con más empleados
   - El promedio de empleados
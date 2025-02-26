# Pandas-Documentacion


¡Claro! A continuación, te proporcionaré una lista de los **comandos más comunes de pandas** junto con **ejemplos prácticos** que ilustran su aplicabilidad en diferentes situaciones. Esto te ayudará a entender cómo usar pandas para manipular y analizar datos.

---

### 📋 **Lista de Comandos Comunes de Pandas**

#### 1. **Creación de DataFrames y Series**
   - `pd.DataFrame()`: Crear un DataFrame desde un diccionario, lista o archivo.
   - `pd.Series()`: Crear una Serie (columna unidimensional).

#### 2. **Lectura y Escritura de Datos**
   - `pd.read_csv()`: Leer un archivo CSV.
   - `pd.read_excel()`: Leer un archivo Excel.
   - `pd.read_sql()`: Leer datos desde una base de datos SQL.
   - `df.to_csv()`: Guardar un DataFrame en un archivo CSV.
   - `df.to_excel()`: Guardar un DataFrame en un archivo Excel.

#### 3. **Exploración de Datos**
   - `df.head()`: Mostrar las primeras filas del DataFrame.
   - `df.tail()`: Mostrar las últimas filas del DataFrame.
   - `df.info()`: Mostrar información sobre el DataFrame (tipos de datos, valores no nulos, etc.).
   - `df.describe()`: Resumen estadístico de las columnas numéricas.
   - `df.shape`: Obtener el número de filas y columnas.
   - `df.columns`: Obtener los nombres de las columnas.

#### 4. **Selección y Filtrado**
   - `df['columna']`: Seleccionar una columna.
   - `df[['col1', 'col2']]`: Seleccionar múltiples columnas.
   - `df.loc[]`: Seleccionar filas y columnas por etiqueta.
   - `df.iloc[]`: Seleccionar filas y columnas por índice.
   - `df.query()`: Filtrar filas usando una expresión.

#### 5. **Manipulación de Datos**
   - `df.drop()`: Eliminar filas o columnas.
   - `df.rename()`: Renombrar columnas.
   - `df.sort_values()`: Ordenar por valores de una columna.
   - `df.fillna()`: Rellenar valores nulos.
   - `df.dropna()`: Eliminar filas o columnas con valores nulos.
   - `df.replace()`: Reemplazar valores.

#### 6. **Agrupación y Agregación**
   - `df.groupby()`: Agrupar datos por una o más columnas.
   - `df.agg()`: Aplicar múltiples funciones de agregación.
   - `df.pivot_table()`: Crear una tabla dinámica.

#### 7. **Combinación de DataFrames**
   - `pd.concat()`: Concatenar DataFrames.
   - `pd.merge()`: Fusionar DataFrames (similar a SQL JOIN).

#### 8. **Series Temporales**
   - `pd.to_datetime()`: Convertir a tipo de dato datetime.
   - `df.resample()`: Remuestrear datos temporales.

#### 9. **Aplicación de Funciones**
   - `df.apply()`: Aplicar una función a una columna o fila.
   - `df.map()`: Mapear valores de una Serie.

---

### 🛠️ **Ejercicios Prácticos Explicados**

#### 1. **Creación de un DataFrame**
   ```python
   import pandas as pd

   # Crear un DataFrame desde un diccionario
   data = {'Nombre': ['Ana', 'Juan', 'María'], 'Edad': [25, 30, 22], 'Ciudad': ['Madrid', 'Barcelona', 'Valencia']}
   df = pd.DataFrame(data)
   print(df)
   ```

   **Salida**:
   ```
     Nombre  Edad      Ciudad
   0    Ana    25      Madrid
   1   Juan    30  Barcelona
   2  María    22   Valencia
   ```

---

#### 2. **Lectura de un Archivo CSV**
   ```python
   # Leer un archivo CSV
   df = pd.read_csv('datos.csv')
   print(df.head())  # Mostrar las primeras 5 filas
   ```

---

#### 3. **Filtrado de Datos**
   ```python
   # Filtrar filas donde la edad sea mayor a 25
   filtro = df[df['Edad'] > 25]
   print(filtro)
   ```

---

#### 4. **Agrupación y Agregación**
   ```python
   # Agrupar por ciudad y calcular la edad promedio
   grupo = df.groupby('Ciudad')['Edad'].mean()
   print(grupo)
   ```

   **Salida**:
   ```
   Ciudad
   Barcelona    30.0
   Madrid       25.0
   Valencia     22.0
   Name: Edad, dtype: float64
   ```

---

#### 5. **Combinación de DataFrames**
   ```python
   # Crear dos DataFrames
   df1 = pd.DataFrame({'A': ['A0', 'A1'], 'B': ['B0', 'B1']})
   df2 = pd.DataFrame({'A': ['A2', 'A3'], 'B': ['B2', 'B3']})

   # Concatenar verticalmente
   resultado = pd.concat([df1, df2], axis=0)
   print(resultado)
   ```

   **Salida**:
   ```
      A   B
   0  A0  B0
   1  A1  B1
   0  A2  B2
   1  A3  B3
   ```

---

#### 6. **Aplicación de Funciones**
   ```python
   # Aplicar una función a una columna
   df['Edad'] = df['Edad'].apply(lambda x: x + 1)  # Incrementar la edad en 1
   print(df)
   ```

---

#### 7. **Manejo de Valores Nulos**
   ```python
   # Rellenar valores nulos con 0
   df['Edad'].fillna(0, inplace=True)
   ```

---

#### 8. **Tabla Dinámica**
   ```python
   # Crear una tabla dinámica
   pivot = df.pivot_table(values='Edad', index='Ciudad', aggfunc='mean')
   print(pivot)
   ```

---

#### 9. **Series Temporales**
   ```python
   # Convertir una columna a datetime
   df['Fecha'] = pd.to_datetime(df['Fecha'])
   ```

---

### 🎯 **Consejos Finales**
- **Practica con datos reales**: Usa datasets de [Kaggle](https://www.kaggle.com/) o [Google Dataset Search](https://datasetsearch.research.google.com/).  

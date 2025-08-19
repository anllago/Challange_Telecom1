# 📊 Análisis de Evasión de Clientes en Telecom X  

## 📌 Descripción del Proyecto  
Este proyecto explora la **evasión de clientes (churn)** en una compañía ficticia de telecomunicaciones llamada **Telecom X**.  
El objetivo principal es **identificar los factores que influyen en la pérdida de clientes** y generar estrategias de retención basadas en los hallazgos.  

La investigación combina **extracción, limpieza, transformación y análisis exploratorio de datos (EDA)** utilizando **Python** y librerías como `pandas`, `matplotlib` y `seaborn`.  

---

## 🎯 Objetivos  
- Analizar patrones de comportamiento en los clientes que cancelaron su servicio.  
- Comparar la evasión en función de variables **categóricas** (género, contrato, método de pago).  
- Estudiar la relación entre la evasión y variables **numéricas** (antigüedad, cargos mensuales, cargos totales).  
- Generar **insights accionables** para reducir la tasa de cancelación.  

---

## 📂 Datos Utilizados  
- **Fuente:** API con registros en formato **JSON**.  
- **Dataset inicial:** 7267 registros y 6 columnas.  
- **Dataset final tras limpieza:** 7043 registros y 20+ columnas.  

### Variables relevantes:  
| Variable         | Descripción                                     |
|------------------|-------------------------------------------------|
| **Churn**        | Cliente se dio de baja (Sí/No)                 |
| **tenure**       | Antigüedad en meses                            |
| **MonthlyCharges** | Cargos mensuales                             |
| **TotalCharges** | Cargos acumulados                              |
| **Contract**     | Tipo de contrato (Mes a mes, 1 año, 2 años)    |
| **PaymentMethod**| Método de pago                                 |
| **InternetService / PhoneService** | Servicios contratados        |

---

## 🔧 Proceso de Preparación  

1. **Extracción:**  
   - Carga de datos en un `DataFrame` con **pandas**.  

2. **Limpieza:**  
   - Eliminación de 224 registros con `Churn` vacío.  
   - Expansión de columnas anidadas con `pd.json_normalize`.  
   - Renombrado de columnas al español.  

3. **Transformación:**  
   - Conversión de `Churn` a binario (1 = Sí, 0 = No).  
   - Creación de variables derivadas, por ejemplo:  
     - `Cargos_Diarios = CargosMensuales / 30`.  

---

## 📊 Análisis Exploratorio de Datos  

### 1. Estadísticas Generales  
- Tasa de evasión: **26.5%**  
- Clientes que permanecieron: **73.5%**  

### 2. Variables Categóricas  
- **Contrato:** *Mes a mes* = mayor evasión.  
- **Método de pago:** *Cheque electrónico* = más probabilidad de baja.  
- **Género:** no es un factor determinante.  

### 3. Variables Numéricas  
- **Antigüedad:** clientes nuevos cancelan más, sobre todo en los primeros meses.  
- **Cargos mensuales:** montos altos están asociados a más evasión.  
- **Cargos totales:** más bajos en clientes que cancelaron (por menor permanencia).  

### 4. Otros Hallazgos  
- Clientes con 1-2 servicios = mayor riesgo de fuga.  
- El riesgo baja entre 3-6 servicios, pero sube ligeramente con 7-8.  
- Correlaciones:  
  - `tenure` ↘ evasión (relación negativa fuerte).  
  - `MonthlyCharges` y `Cargos_Diarios` ↗ evasión (relación positiva).  

---

## ✅ Conclusiones  
1. Los contratos *mes a mes* concentran la mayor fuga.  
2. Los clientes nuevos son los más vulnerables.  
3. El método de pago es un factor clave: *cheque electrónico* = mayor churn.  
4. Precios altos generan insatisfacción.  
5. El número de servicios influye: pocos servicios = mayor evasión.  

---

## 🚀 Recomendaciones  
- Incentivar **contratos de largo plazo** con beneficios.  
- Implementar un **programa de bienvenida** para nuevos clientes.  
- Promover **pagos automáticos** frente a cheques electrónicos.  
- Ofrecer **paquetes de servicios personalizados**.  
- Desarrollar un **modelo predictivo de churn** para detección temprana.  

---

## 🛠️ Tecnologías Utilizadas  
- **Python 3.11**  
- **pandas** para manipulación de datos  
- **numpy** para operaciones numéricas  
- **matplotlib** y **seaborn** para visualización  
- **scikit-learn** (en fases futuras para modelado predictivo)  

---

## 📈 Visualizaciones Incluidas  
- Gráficos de barras y pastel para variables categóricas.  
- Histogramas y boxplots para variables numéricas.  
- Mapas de calor de correlaciones.  

---

## 📌 Próximos Pasos  
- Implementar modelos de **Machine Learning** para predicción de churn.  
- Crear un **dashboard interactivo** en Power BI o Streamlit.  
- Evaluar el impacto financiero de la evasión con métricas de ingresos.  

---

👨‍💻 **Autor:** Andrés Llanos  
📅 **Año:** 2025  


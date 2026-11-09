# Modelo Relacional de Bases de Datos 13



## Descripción



Este documento detalla el esquema y la estructura del modelo relacional de bases de datos para un sistema de alquiler de vehículos, enfocado en el control de sucursales, clientes, vehículos, contratos de alquiler y siniestros.

---

## Estructura de Tablas y Atributos



### 1. Sucursal



* **PK (Clave Primaria):** `id_codigo_sucursal`


* **Atributos:**
* `nombre`


* `dirección`


* `ciudad`


* `codigo_postal`





### 2. Cliente



* **PK (Clave Primaria):** `id_DNI_pasaporte`


* **Atributos:**
* `nombre`


* `tarjeta_crédito`


* `licencia_conducir`


* `fecha_vencimiento_licencia`


* `тельéfono` (o `teléfono`)





### 3. Vehiculo



* **PK (Clave Primaria):** `id_Patente`


* **Atributos:**
* `marca`


* `categoria`


* `kilometraje`


* `numero_chasis`


* `modelo`





### 4. Contraro-Alquiler



* **PK (Clave Primaria):** `id_contrato`


* **Atributos:**
* `fecha_devolucion_prevista`


* `fecha_devolucion_real`


* `fecha_hora_retiro`




* **FK (Claves Foráneas):**
* `id_DNI_pasaporte` (asociado a la tabla Cliente)


* `id_Patente` (asociado a la tabla Vehiculo)


* *(Nota: También se visualizan relaciones de sucursal de retiro/devolución vinculadas al contrato)*





### 5. Siniestro



* **PK (Clave Primaria):** `id_Siniestro`


* **Atributos:**
* `fecha`


* `descripción`


* `costo_estimado`


* `compañía_aseguradora`




* **FK (Claves Foráneas):**
* `id_Contrato` (asociado a la tabla Contraro-Alquiler)





---

## Relaciones Principales



* **Sucursal y Contrato-Alquiler:** Las sucursales gestionan el retiro y la recepción de los vehículos mediante los contratos registrados.


* **Cliente y Contrato-Alquiler:** Un cliente puede realizar múltiples contratos de alquiler identificándose por su `id_DNI_pasaporte`.


* **Vehiculo y Contrato-Alquiler:** Los vehículos se rentan a través de contratos asociados a su `id_Patente`.


* **Contrato-Alquiler y Siniestro:** Los siniestros o incidentes ocurridos durante un alquiler se registran y vinculan directamente al contrato mediante `id_Contrato`.

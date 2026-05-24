# ARIES - ARchivo de Inventarios ESpañoles

Plataforma para la recuperación, indexación y consulta del patrimonio documental de los siglos XVI y XVII, originalmente recopilado por Anastasio Rojo Vega.

Link de acceso https://g9a3a93d5adcf67-testdatabase1.adb.eu-madrid-1.oraclecloudapps.com/ords/r/tfg/aries/home?session=306112938261044

## Arquitectura y Tecnologías
* **Infraestructura Cloud:** Oracle Cloud Infrastructure (OCI) - Always Free.
* **Motor de Base de Datos:** Oracle Autonomous Database 23ai (Autonomous Transaction Processing).
* **Plataforma de Aplicación:** Oracle APEX.
* **Servicios de Red:** Oracle REST Data Services (ORDS).

## Procedimiento de Despliegue (SysAdmin)

Para replicar esta infraestructura en un entorno limpio de Oracle Cloud, siga estrictamente este orden secuencial:

### 1. Preparación del Backend (Base de Datos)
1. Acceda a su instancia de Oracle Autonomous Database a través de **SQL Workshop** en APEX o mediante **Oracle SQL Developer**.
2. Ejecute el script `/database/Tablas.sql` para levantar la estructura relacional de las 10 tablas en 3FN.
3. Ejecute el script `/database/Vistas.sql` para compilar la vista `ARTICULOS_SEARCH_V` y `ARTICULOS_EXACTA_V`

### 2. Importación del Frontend (Aplicación Web)
1. Inicie sesión en su Workspace de Oracle APEX.
2. Diríjase a **App Builder** y seleccione **Import**.
3. Suba el archivo `/app/ARIES.sql` (asegúrese de mantener la opción de importar Componentes Compartidos activa).
4. El motor de APEX enlazará automáticamente la `Search Region` de la interfaz con la vista relacional compilada en el paso anterior.

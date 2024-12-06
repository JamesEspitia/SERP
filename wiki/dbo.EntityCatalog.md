## Descripción

Un catálogo de entidades representa una tabla que almacena todas las entidades 
(modelos) disponibles en el sistema Django, facilitando su gestión y referencia.

¿Para qué sirve?:

1. Mantener un registro centralizado de todas las entidades del sistema.

2. Facilitar la gestión y el mantenimiento de la estructura de la base de datos.

3. Permitir la referencia dinámica a diferentes modelos del sistema.

4. Proveer una base para la implementación de funcionalidades genéricas.

5. Apoyar en la documentación y organización del sistema.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T20:22:26.277|
|Última Modificación|2024-12-05T22:13:57.127|
|Propietario|dbo|
|Pertenece Al Esquema|Sí|
|Esquema|dbo|
|Objeto Del Sistema|No|
|Contiene Desencadenadores Después De|No|
|Contiene Desencadenadores De Insersión|No|
|Contiene Desencadenadores De Borrado|No|
|Contiene Desencadenadores De Sustitución|No|
|Contiene Desencadenadores De Actualización|No|
|Tiene Índices|Sí|
|Es Indexable|Sí|
|Tiene Índices Agrupados|Sí|
|Tiene Índices No Agrupados|Sí|
|Tiene Índices Agrupados Primarios|Sí|
|Tiene Columnas No Agrupadas Para Reindexar|No|
|Tiene Índices XML|No|
|Tiene Índice Amontonado|No|
|Tiene Datos XML|No|
|Tiene Datos Espaciales|No|
|Estado De Comparación Con Nulos|Sí|
|Estado De Comillas Delimitadoras|Sí|
|Grupo De Archivo De Texto|PRIMARY|
|Replicada|No|
|Grupo De Archivos|PRIMARY|
|Esquema De Partición||
|Está Particionada|No|

## Columnas

|Nombre|Descripción|Llave Primaria|Llave Foránea|Permite Nulos|Autonumérica|Inicio Autonumérico|Incremento Autonumérico|Tipo De Dato|Esquema Del Tipo De Dato|Tipo De Dato Del Sistema|Tamaño|Precisión|Escala|Intercalación|Calculada|Relleno Ansi|Columna De Indentidad De Fila|Texto Calculado|Persistida|Nombre Del Valor Por Defecto|Esquema Predeterminado|Nombre Restricción Predeterminada|Regla|Esquema De La Regla|Determinística|Precisa|No Para Replicación|Texto Completo Indexado|Documento XML|Espacio De Nombres Del Esquema XML|Esquema Del Espacio De Nombres Del Esquema XML|
|------|-----------|--------------|-------------|-------------|------------|-------------------|-----------------------|------------|------------------------|------------------------|------|---------|------|-------------|---------|------------|-----------------------------|---------------|----------|----------------------------|----------------------|---------------------------------|-----|-------------------|--------------|-------|-------------------|-----------------------|-------------|----------------------------------|----------------------------------------------|
|id_entit|Identificador único para el elemento del catálogo de entidades.|Sí|No|No|Sí|1|1|int|sys|int|4|10|0||No|No|No||No||||||No|No|False|No|No|||
|entit_name|Nombre del modelo Django asociado.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|entit_descrip|Descripción del elemento del catálogo de entidades.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|entit_active|Indica si el elemento del catálogo está activo (1) o inactivo (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_EntityCatalog_entit_active|||No|No|False|No|No|||
|entit_config|Configuración adicional para el elemento del catálogo.|No|No|Sí|No|0|0|nvarchar|sys|nvarchar|-1|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_EntityCatalog|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_EntityCatalog_entit_name|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[EntityCatalog](
	[id_entit] [int] IDENTITY(1,1) NOT NULL,
	[entit_name] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[entit_descrip] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[entit_active] [bit] NOT NULL,
	[entit_config] [nvarchar](max) COLLATE Latin1_General_CS_AS NULL,
 CONSTRAINT [PK_EntityCatalog] PRIMARY KEY CLUSTERED 
(
	[id_entit] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_EntityCatalog_entit_name] UNIQUE NONCLUSTERED 
(
	[entit_name] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
ALTER TABLE [dbo].[EntityCatalog] ADD  CONSTRAINT [DF_EntityCatalog_entit_active]  DEFAULT ((1)) FOR [entit_active]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para el elemento del catálogo de entidades.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'COLUMN',@level2name=N'id_entit'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre del modelo Django asociado.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'COLUMN',@level2name=N'entit_name'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Descripción del elemento del catálogo de entidades.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'COLUMN',@level2name=N'entit_descrip'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si el elemento del catálogo está activo (1) o inactivo (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'COLUMN',@level2name=N'entit_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el elemento del catálogo se crea como activo (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'CONSTRAINT',@level2name=N'DF_EntityCatalog_entit_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Configuración adicional para el elemento del catálogo.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'COLUMN',@level2name=N'entit_config'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'CONSTRAINT',@level2name=N'PK_EntityCatalog'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para el nombre de la entidad.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog', @level2type=N'CONSTRAINT',@level2name=N'UQ_EntityCatalog_entit_name'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Un catálogo de entidades representa una tabla que almacena todas las entidades 
(modelos) disponibles en el sistema Django, facilitando su gestión y referencia.

¿Para qué sirve?:

1. Mantener un registro centralizado de todas las entidades del sistema.

2. Facilitar la gestión y el mantenimiento de la estructura de la base de datos.

3. Permitir la referencia dinámica a diferentes modelos del sistema.

4. Proveer una base para la implementación de funcionalidades genéricas.

5. Apoyar en la documentación y organización del sistema.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'EntityCatalog'
GO
~~~


## Usada Por

[dbo.PermiRole](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiRole)

[dbo.PermiRoleRecord](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiRoleRecord)

[dbo.PermiUser](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiUser)

[dbo.PermiUserRecord](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiUserRecord)


## Depende De


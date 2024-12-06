## Descripción

Un permiso representa los diferentes niveles de acceso y operaciones
que pueden realizarse sobre una entidad del sistema.

¿Para qué sirve?:

1. Control granular de acciones sobre entidades del sistema.

2. Definición de permisos específicos para operaciones CRUD.

3. Gestión de capacidades de importación y exportación de datos.

4. Implementación de políticas de seguridad y acceso.

5. Configuración flexible de permisos por funcionalidad.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T20:38:17.063|
|Última Modificación|2024-12-05T22:13:57.123|
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
|Tiene Índices No Agrupados|No|
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
|id_permi|Identificador único para el permiso.|Sí|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|name|Nombre descriptivo del permiso.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|description|Descripción detallada del permiso y su propósito.|No|No|Sí|No|0|0|nvarchar|sys|nvarchar|-1|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|can_create|Permite crear nuevos registros.|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Permission_can_create|||No|No|False|No|No|||
|can_read|Permite ver registros existentes.|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Permission_can_read|||No|No|False|No|No|||
|can_update|Permite modificar registros existentes.|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Permission_can_update|||No|No|False|No|No|||
|can_delete|Permite eliminar registros existentes.|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Permission_can_delete|||No|No|False|No|No|||
|can_import|Permite importar datos masivamente.|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Permission_can_import|||No|No|False|No|No|||
|can_export|Permite exportar datos del sistema.|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Permission_can_export|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_Permission|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Permission](
	[id_permi] [bigint] IDENTITY(1,1) NOT NULL,
	[name] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[description] [nvarchar](max) COLLATE Latin1_General_CS_AS NULL,
	[can_create] [bit] NOT NULL,
	[can_read] [bit] NOT NULL,
	[can_update] [bit] NOT NULL,
	[can_delete] [bit] NOT NULL,
	[can_import] [bit] NOT NULL,
	[can_export] [bit] NOT NULL,
 CONSTRAINT [PK_Permission] PRIMARY KEY CLUSTERED 
(
	[id_permi] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
ALTER TABLE [dbo].[Permission] ADD  CONSTRAINT [DF_Permission_can_create]  DEFAULT ((0)) FOR [can_create]
GO
ALTER TABLE [dbo].[Permission] ADD  CONSTRAINT [DF_Permission_can_read]  DEFAULT ((0)) FOR [can_read]
GO
ALTER TABLE [dbo].[Permission] ADD  CONSTRAINT [DF_Permission_can_update]  DEFAULT ((0)) FOR [can_update]
GO
ALTER TABLE [dbo].[Permission] ADD  CONSTRAINT [DF_Permission_can_delete]  DEFAULT ((0)) FOR [can_delete]
GO
ALTER TABLE [dbo].[Permission] ADD  CONSTRAINT [DF_Permission_can_import]  DEFAULT ((0)) FOR [can_import]
GO
ALTER TABLE [dbo].[Permission] ADD  CONSTRAINT [DF_Permission_can_export]  DEFAULT ((0)) FOR [can_export]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para el permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'id_permi'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre descriptivo del permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'name'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Descripción detallada del permiso y su propósito.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'description'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permite crear nuevos registros.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'can_create'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto no permite crear nuevos registros (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'CONSTRAINT',@level2name=N'DF_Permission_can_create'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permite ver registros existentes.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'can_read'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto no permite ver registros existentes (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'CONSTRAINT',@level2name=N'DF_Permission_can_read'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permite modificar registros existentes.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'can_update'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto no permite modificar registros existentes (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'CONSTRAINT',@level2name=N'DF_Permission_can_update'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permite eliminar registros existentes.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'can_delete'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto no permite eliminar registros existentes (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'CONSTRAINT',@level2name=N'DF_Permission_can_delete'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permite importar datos masivamente.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'can_import'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto no permite importar datos masivamente (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'CONSTRAINT',@level2name=N'DF_Permission_can_import'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permite exportar datos del sistema.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'COLUMN',@level2name=N'can_export'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto no permite exportar datos del sistema (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'CONSTRAINT',@level2name=N'DF_Permission_can_export'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission', @level2type=N'CONSTRAINT',@level2name=N'PK_Permission'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Un permiso representa los diferentes niveles de acceso y operaciones
que pueden realizarse sobre una entidad del sistema.

¿Para qué sirve?:

1. Control granular de acciones sobre entidades del sistema.

2. Definición de permisos específicos para operaciones CRUD.

3. Gestión de capacidades de importación y exportación de datos.

4. Implementación de políticas de seguridad y acceso.

5. Configuración flexible de permisos por funcionalidad.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Permission'
GO
~~~


## Usada Por

[dbo.PermiRole](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiRole)

[dbo.PermiRoleRecord](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiRoleRecord)

[dbo.PermiUser](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiUser)

[dbo.PermiUserRecord](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiUserRecord)


## Depende De


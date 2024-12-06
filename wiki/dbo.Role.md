## Descripción

Un rol representa un conjunto de permisos y responsabilidades que pueden
ser asignados a usuarios dentro de una compañía específica.

¿Para qué sirve?:

1. Definición de niveles de acceso y permisos por compañía.

2. Agrupación de funcionalidades y accesos para asignación eficiente.

3. Control granular de las capacidades de los usuarios en el sistema.

4. Simplificación de la gestión de permisos por grupos de usuarios.

5. Estandarización de roles y responsabilidades dentro de cada compañía.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T20:52:32.233|
|Última Modificación|2024-12-05T22:03:56.407|
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
|id_role|Identificador único para el rol.|Sí|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|company_id|Compañía a la que pertenece este rol.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|role_name|Nombre descriptivo del rol.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|role_code|Código único del rol.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|role_description|Descripción detallada del rol y sus responsabilidades.|No|No|Sí|No|0|0|nvarchar|sys|nvarchar|-1|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|role_active|Indica si el rol está activo (1) o inactivo (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Role_role_active|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_Role|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_Company_RoleCode|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Role](
	[id_role] [bigint] IDENTITY(1,1) NOT NULL,
	[company_id] [bigint] NOT NULL,
	[role_name] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[role_code] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[role_description] [nvarchar](max) COLLATE Latin1_General_CS_AS NULL,
	[role_active] [bit] NOT NULL,
 CONSTRAINT [PK_Role] PRIMARY KEY CLUSTERED 
(
	[id_role] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_Company_RoleCode] UNIQUE NONCLUSTERED 
(
	[company_id] ASC,
	[role_code] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
ALTER TABLE [dbo].[Role] ADD  CONSTRAINT [DF_Role_role_active]  DEFAULT ((1)) FOR [role_active]
GO
ALTER TABLE [dbo].[Role]  WITH CHECK ADD  CONSTRAINT [FK_Role_Company] FOREIGN KEY([company_id])
REFERENCES [dbo].[Company] ([id_compa])
GO
ALTER TABLE [dbo].[Role] CHECK CONSTRAINT [FK_Role_Company]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para el rol.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'COLUMN',@level2name=N'id_role'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Compañía a la que pertenece este rol.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'COLUMN',@level2name=N'company_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre descriptivo del rol.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'COLUMN',@level2name=N'role_name'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Código único del rol.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'COLUMN',@level2name=N'role_code'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Descripción detallada del rol y sus responsabilidades.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'COLUMN',@level2name=N'role_description'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si el rol está activo (1) o inactivo (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'COLUMN',@level2name=N'role_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el rol se crea como activo (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'CONSTRAINT',@level2name=N'DF_Role_role_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'CONSTRAINT',@level2name=N'PK_Role'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para la combinación de ID de compañía y código de rol.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'CONSTRAINT',@level2name=N'UQ_Company_RoleCode'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Un rol representa un conjunto de permisos y responsabilidades que pueden
ser asignados a usuarios dentro de una compañía específica.

¿Para qué sirve?:

1. Definición de niveles de acceso y permisos por compañía.

2. Agrupación de funcionalidades y accesos para asignación eficiente.

3. Control granular de las capacidades de los usuarios en el sistema.

4. Simplificación de la gestión de permisos por grupos de usuarios.

5. Estandarización de roles y responsabilidades dentro de cada compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia a la compañía en la tabla Company.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Role', @level2type=N'CONSTRAINT',@level2name=N'FK_Role_Company'
GO
~~~


## Usada Por

[dbo.PermiRole](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiRole)

[dbo.PermiRoleRecord](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiRoleRecord)


## Depende De

[dbo.Company](https://github.com/JamesEspitia/SERP/wiki/dbo.Company)


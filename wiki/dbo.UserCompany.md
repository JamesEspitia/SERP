## Descripción

Representa la relación entre un usuario y una compañía, permitiendo gestionar
el acceso de usuarios a múltiples compañías en el sistema.

¿Para qué sirve?:

1. Gestión de permisos de usuarios por compañía.

2. Control de acceso multiempresa para cada usuario.

3. Seguimiento de actividades de usuarios por compañía.

4. Configuración de preferencias específicas por usuario y compañía.

5. Soporte para roles y responsabilidades diferentes en cada compañía.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T21:21:40.470|
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
|Tiene Índices No Agrupados|Sí|
|Tiene Índices Agrupados Primarios|Sí|
|Tiene Columnas No Agrupadas Para Reindexar|No|
|Tiene Índices XML|No|
|Tiene Índice Amontonado|No|
|Tiene Datos XML|No|
|Tiene Datos Espaciales|No|
|Estado De Comparación Con Nulos|Sí|
|Estado De Comillas Delimitadoras|Sí|
|Grupo De Archivo De Texto||
|Replicada|No|
|Grupo De Archivos|PRIMARY|
|Esquema De Partición||
|Está Particionada|No|

## Columnas

|Nombre|Descripción|Llave Primaria|Llave Foránea|Permite Nulos|Autonumérica|Inicio Autonumérico|Incremento Autonumérico|Tipo De Dato|Esquema Del Tipo De Dato|Tipo De Dato Del Sistema|Tamaño|Precisión|Escala|Intercalación|Calculada|Relleno Ansi|Columna De Indentidad De Fila|Texto Calculado|Persistida|Nombre Del Valor Por Defecto|Esquema Predeterminado|Nombre Restricción Predeterminada|Regla|Esquema De La Regla|Determinística|Precisa|No Para Replicación|Texto Completo Indexado|Documento XML|Espacio De Nombres Del Esquema XML|Esquema Del Espacio De Nombres Del Esquema XML|
|------|-----------|--------------|-------------|-------------|------------|-------------------|-----------------------|------------|------------------------|------------------------|------|---------|------|-------------|---------|------------|-----------------------------|---------------|----------|----------------------------|----------------------|---------------------------------|-----|-------------------|--------------|-------|-------------------|-----------------------|-------------|----------------------------------|----------------------------------------------|
|id_useco|Identificador único para la relación usuario-compañía.|Sí|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|user_id|Usuario asociado a la compañía.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|company_id|Compañía asociada al usuario.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|useco_active|Indica si la relación usuario-compañía está activa (1) o inactiva (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_UserCompany_useco_active|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_UserCompany|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_User_Company|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[UserCompany](
	[id_useco] [bigint] IDENTITY(1,1) NOT NULL,
	[user_id] [bigint] NOT NULL,
	[company_id] [bigint] NOT NULL,
	[useco_active] [bit] NOT NULL,
 CONSTRAINT [PK_UserCompany] PRIMARY KEY CLUSTERED 
(
	[id_useco] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_User_Company] UNIQUE NONCLUSTERED 
(
	[user_id] ASC,
	[company_id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
ALTER TABLE [dbo].[UserCompany] ADD  CONSTRAINT [DF_UserCompany_useco_active]  DEFAULT ((1)) FOR [useco_active]
GO
ALTER TABLE [dbo].[UserCompany]  WITH CHECK ADD  CONSTRAINT [FK_UserCompany_Company] FOREIGN KEY([company_id])
REFERENCES [dbo].[Company] ([id_compa])
GO
ALTER TABLE [dbo].[UserCompany] CHECK CONSTRAINT [FK_UserCompany_Company]
GO
ALTER TABLE [dbo].[UserCompany]  WITH CHECK ADD  CONSTRAINT [FK_UserCompany_User] FOREIGN KEY([user_id])
REFERENCES [dbo].[User] ([id_user])
GO
ALTER TABLE [dbo].[UserCompany] CHECK CONSTRAINT [FK_UserCompany_User]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para la relación usuario-compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'COLUMN',@level2name=N'id_useco'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Usuario asociado a la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'COLUMN',@level2name=N'user_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Compañía asociada al usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'COLUMN',@level2name=N'company_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si la relación usuario-compañía está activa (1) o inactiva (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'COLUMN',@level2name=N'useco_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto la relación usuario-compañía se crea como activa (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'CONSTRAINT',@level2name=N'DF_UserCompany_useco_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'CONSTRAINT',@level2name=N'PK_UserCompany'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para la combinación de usuario y compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'CONSTRAINT',@level2name=N'UQ_User_Company'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Representa la relación entre un usuario y una compañía, permitiendo gestionar
el acceso de usuarios a múltiples compañías en el sistema.

¿Para qué sirve?:

1. Gestión de permisos de usuarios por compañía.

2. Control de acceso multiempresa para cada usuario.

3. Seguimiento de actividades de usuarios por compañía.

4. Configuración de preferencias específicas por usuario y compañía.

5. Soporte para roles y responsabilidades diferentes en cada compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia a la compañía en la tabla Company.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'CONSTRAINT',@level2name=N'FK_UserCompany_Company'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia al usuario en la tabla User.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'UserCompany', @level2type=N'CONSTRAINT',@level2name=N'FK_UserCompany_User'
GO
~~~


## Usada Por

[dbo.PermiUser](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiUser)

[dbo.PermiUserRecord](https://github.com/JamesEspitia/SERP/wiki/dbo.PermiUserRecord)


## Depende De

[dbo.Company](https://github.com/JamesEspitia/SERP/wiki/dbo.Company)

[dbo.User](https://github.com/JamesEspitia/SERP/wiki/dbo.User)


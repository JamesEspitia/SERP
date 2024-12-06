## Descripción

Representa los permisos específicos asignados a un usuario para una 
entidad particular y un registro específico dentro de una compañía.

¿Para qué sirve?:

1. Asignación de permisos específicos por usuario y entidad a nivel de registro.

2. Control granular de accesos a nivel de usuario-compañía y registro.

3. Personalización de capacidades por entidad y registro del sistema.

4. Gestión detallada de privilegios por usuario a nivel de registro.

5. Implementación de políticas de seguridad específicas por entidad y registro.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T22:13:57.110|
|Última Modificación|2024-12-05T22:13:57.110|
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
|id_peusr|Identificador único para el permiso de usuario.|No|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|usercompany_id|Relación usuario-compañía a la que se asigna el permiso.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|permission_id|Permiso asignado al usuario.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|entitycatalog_id|Entidad sobre la que se aplica el permiso.|No|Sí|No|No|0|0|int|sys|int|4|10|0||No|No|No||No||||||No|No|False|No|No|||
|peusr_record|Identificador del registro específico de la entidad al que aplica el permiso.|No|No|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|peusr_include|Indica si el permiso se incluye (1) o se excluye (0) para el usuario.|Sí|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_PermiUserRecord_peusr_include|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_PermiUserRecord|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_UserCompany_Permission_Entity_Record|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[PermiUserRecord](
	[id_peusr] [bigint] IDENTITY(1,1) NOT NULL,
	[usercompany_id] [bigint] NOT NULL,
	[permission_id] [bigint] NOT NULL,
	[entitycatalog_id] [int] NOT NULL,
	[peusr_record] [bigint] NOT NULL,
	[peusr_include] [bit] NOT NULL,
 CONSTRAINT [PK_PermiUserRecord] PRIMARY KEY CLUSTERED 
(
	[peusr_include] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_UserCompany_Permission_Entity_Record] UNIQUE NONCLUSTERED 
(
	[usercompany_id] ASC,
	[permission_id] ASC,
	[entitycatalog_id] ASC,
	[peusr_record] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
ALTER TABLE [dbo].[PermiUserRecord] ADD  CONSTRAINT [DF_PermiUserRecord_peusr_include]  DEFAULT ((1)) FOR [peusr_include]
GO
ALTER TABLE [dbo].[PermiUserRecord]  WITH CHECK ADD  CONSTRAINT [FK_PermiUserRecord_EntityCatalog] FOREIGN KEY([entitycatalog_id])
REFERENCES [dbo].[EntityCatalog] ([id_entit])
GO
ALTER TABLE [dbo].[PermiUserRecord] CHECK CONSTRAINT [FK_PermiUserRecord_EntityCatalog]
GO
ALTER TABLE [dbo].[PermiUserRecord]  WITH CHECK ADD  CONSTRAINT [FK_PermiUserRecord_Permission] FOREIGN KEY([permission_id])
REFERENCES [dbo].[Permission] ([id_permi])
GO
ALTER TABLE [dbo].[PermiUserRecord] CHECK CONSTRAINT [FK_PermiUserRecord_Permission]
GO
ALTER TABLE [dbo].[PermiUserRecord]  WITH CHECK ADD  CONSTRAINT [FK_PermiUserRecord_UserCompany] FOREIGN KEY([usercompany_id])
REFERENCES [dbo].[UserCompany] ([id_useco])
GO
ALTER TABLE [dbo].[PermiUserRecord] CHECK CONSTRAINT [FK_PermiUserRecord_UserCompany]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para el permiso de usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'COLUMN',@level2name=N'id_peusr'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Relación usuario-compañía a la que se asigna el permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'COLUMN',@level2name=N'usercompany_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permiso asignado al usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'COLUMN',@level2name=N'permission_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Entidad sobre la que se aplica el permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'COLUMN',@level2name=N'entitycatalog_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador del registro específico de la entidad al que aplica el permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'COLUMN',@level2name=N'peusr_record'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si el permiso se incluye (1) o se excluye (0) para el usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'COLUMN',@level2name=N'peusr_include'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el permiso se incluye (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'CONSTRAINT',@level2name=N'DF_PermiUserRecord_peusr_include'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'CONSTRAINT',@level2name=N'PK_PermiUserRecord'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para la combinación de usuario-compañía, permiso, entidad y registro.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'CONSTRAINT',@level2name=N'UQ_UserCompany_Permission_Entity_Record'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Representa los permisos específicos asignados a un usuario para una 
entidad particular y un registro específico dentro de una compañía.

¿Para qué sirve?:

1. Asignación de permisos específicos por usuario y entidad a nivel de registro.

2. Control granular de accesos a nivel de usuario-compañía y registro.

3. Personalización de capacidades por entidad y registro del sistema.

4. Gestión detallada de privilegios por usuario a nivel de registro.

5. Implementación de políticas de seguridad específicas por entidad y registro.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia a la entidad en la tabla EntityCatalog.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'CONSTRAINT',@level2name=N'FK_PermiUserRecord_EntityCatalog'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia al permiso en la tabla Permission.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'CONSTRAINT',@level2name=N'FK_PermiUserRecord_Permission'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia a la relación usuario-compañía en la tabla UserCompany.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiUserRecord', @level2type=N'CONSTRAINT',@level2name=N'FK_PermiUserRecord_UserCompany'
GO
~~~


## Usada Por


## Depende De

[dbo.EntityCatalog](https://github.com/JamesEspitia/SERP/wiki/dbo.EntityCatalog)

[dbo.Permission](https://github.com/JamesEspitia/SERP/wiki/dbo.Permission)

[dbo.UserCompany](https://github.com/JamesEspitia/SERP/wiki/dbo.UserCompany)


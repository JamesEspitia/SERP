## Descripción

Representa los permisos específicos asignados a un rol para una 
entidad y registro particular dentro del sistema.

¿Para qué sirve?:

1. Asignación de permisos específicos por rol, entidad y registro.

2. Control granular de accesos a nivel de rol y registro.

3. Personalización de capacidades por entidad y registro del sistema.

4. Gestión detallada de privilegios por rol y registro específico.

5. Implementación de políticas de seguridad específicas por rol, entidad y registro.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T22:03:56.407|
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
|Grupo De Archivo De Texto||
|Replicada|No|
|Grupo De Archivos|PRIMARY|
|Esquema De Partición||
|Está Particionada|No|

## Columnas

|Nombre|Descripción|Llave Primaria|Llave Foránea|Permite Nulos|Autonumérica|Inicio Autonumérico|Incremento Autonumérico|Tipo De Dato|Esquema Del Tipo De Dato|Tipo De Dato Del Sistema|Tamaño|Precisión|Escala|Intercalación|Calculada|Relleno Ansi|Columna De Indentidad De Fila|Texto Calculado|Persistida|Nombre Del Valor Por Defecto|Esquema Predeterminado|Nombre Restricción Predeterminada|Regla|Esquema De La Regla|Determinística|Precisa|No Para Replicación|Texto Completo Indexado|Documento XML|Espacio De Nombres Del Esquema XML|Esquema Del Espacio De Nombres Del Esquema XML|
|------|-----------|--------------|-------------|-------------|------------|-------------------|-----------------------|------------|------------------------|------------------------|------|---------|------|-------------|---------|------------|-----------------------------|---------------|----------|----------------------------|----------------------|---------------------------------|-----|-------------------|--------------|-------|-------------------|-----------------------|-------------|----------------------------------|----------------------------------------------|
|id_perrc|Identificador único para el permiso de rol por registro.|No|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|role_id|Rol al que se asigna el permiso.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|permission_id|Permiso asignado al rol.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|entitycatalog_id|Entidad sobre la que se aplica el permiso.|No|Sí|No|No|0|0|int|sys|int|4|10|0||No|No|No||No||||||No|No|False|No|No|||
|perrc_record|Identificador del registro específico al que se aplica el permiso.|No|No|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|perrc_include|Indica si el permiso se incluye (1) o se excluye (0) para el rol y registro.|Sí|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_PermiRoleRecord_perrc_include|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_PermiRoleRecord|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_PermiRoleRecord_role_id_permission_id_entitycatalog_id_perrc_record|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[PermiRoleRecord](
	[id_perrc] [bigint] IDENTITY(1,1) NOT NULL,
	[role_id] [bigint] NOT NULL,
	[permission_id] [bigint] NOT NULL,
	[entitycatalog_id] [int] NOT NULL,
	[perrc_record] [bigint] NOT NULL,
	[perrc_include] [bit] NOT NULL,
 CONSTRAINT [PK_PermiRoleRecord] PRIMARY KEY CLUSTERED 
(
	[perrc_include] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_PermiRoleRecord_role_id_permission_id_entitycatalog_id_perrc_record] UNIQUE NONCLUSTERED 
(
	[role_id] ASC,
	[permission_id] ASC,
	[entitycatalog_id] ASC,
	[perrc_record] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
ALTER TABLE [dbo].[PermiRoleRecord] ADD  CONSTRAINT [DF_PermiRoleRecord_perrc_include]  DEFAULT ((1)) FOR [perrc_include]
GO
ALTER TABLE [dbo].[PermiRoleRecord]  WITH CHECK ADD  CONSTRAINT [FK_PermiRoleRecord_EntityCatalog] FOREIGN KEY([entitycatalog_id])
REFERENCES [dbo].[EntityCatalog] ([id_entit])
GO
ALTER TABLE [dbo].[PermiRoleRecord] CHECK CONSTRAINT [FK_PermiRoleRecord_EntityCatalog]
GO
ALTER TABLE [dbo].[PermiRoleRecord]  WITH CHECK ADD  CONSTRAINT [FK_PermiRoleRecord_Permission] FOREIGN KEY([permission_id])
REFERENCES [dbo].[Permission] ([id_permi])
GO
ALTER TABLE [dbo].[PermiRoleRecord] CHECK CONSTRAINT [FK_PermiRoleRecord_Permission]
GO
ALTER TABLE [dbo].[PermiRoleRecord]  WITH CHECK ADD  CONSTRAINT [FK_PermiRoleRecord_Role] FOREIGN KEY([role_id])
REFERENCES [dbo].[Role] ([id_role])
GO
ALTER TABLE [dbo].[PermiRoleRecord] CHECK CONSTRAINT [FK_PermiRoleRecord_Role]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para el permiso de rol por registro.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'COLUMN',@level2name=N'id_perrc'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Rol al que se asigna el permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'COLUMN',@level2name=N'role_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Permiso asignado al rol.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'COLUMN',@level2name=N'permission_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Entidad sobre la que se aplica el permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'COLUMN',@level2name=N'entitycatalog_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador del registro específico al que se aplica el permiso.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'COLUMN',@level2name=N'perrc_record'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si el permiso se incluye (1) o se excluye (0) para el rol y registro.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'COLUMN',@level2name=N'perrc_include'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el permiso se incluye (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'CONSTRAINT',@level2name=N'DF_PermiRoleRecord_perrc_include'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'CONSTRAINT',@level2name=N'PK_PermiRoleRecord'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para la combinación de rol, permiso, entidad y registro.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'CONSTRAINT',@level2name=N'UQ_PermiRoleRecord_role_id_permission_id_entitycatalog_id_perrc_record'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Representa los permisos específicos asignados a un rol para una 
entidad y registro particular dentro del sistema.

¿Para qué sirve?:

1. Asignación de permisos específicos por rol, entidad y registro.

2. Control granular de accesos a nivel de rol y registro.

3. Personalización de capacidades por entidad y registro del sistema.

4. Gestión detallada de privilegios por rol y registro específico.

5. Implementación de políticas de seguridad específicas por rol, entidad y registro.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia a la entidad en la tabla EntityCatalog.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'CONSTRAINT',@level2name=N'FK_PermiRoleRecord_EntityCatalog'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia al permiso en la tabla Permission.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'CONSTRAINT',@level2name=N'FK_PermiRoleRecord_Permission'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia al rol en la tabla Role.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PermiRoleRecord', @level2type=N'CONSTRAINT',@level2name=N'FK_PermiRoleRecord_Role'
GO
~~~


## Usada Por


## Depende De

[dbo.EntityCatalog](https://github.com/JamesEspitia/SERP/wiki/dbo.EntityCatalog)

[dbo.Permission](https://github.com/JamesEspitia/SERP/wiki/dbo.Permission)

[dbo.Role](https://github.com/JamesEspitia/SERP/wiki/dbo.Role)


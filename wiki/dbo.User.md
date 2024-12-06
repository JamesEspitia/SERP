## Descripción

Un usuario representa una persona que interactúa con el sistema,
con sus credenciales y datos básicos de acceso.

¿Para qué sirve?:

1. Gestión de acceso y autenticación en el sistema.

2. Almacenamiento de información básica de los usuarios.

3. Control de estados y permisos de usuarios.

4. Seguimiento de actividad y auditoría de usuarios.

5. Base para la personalización de la experiencia de usuario.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T21:05:12.777|
|Última Modificación|2024-12-05T21:21:40.473|
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
|id_user|Identificador único para el usuario.|Sí|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|user_username|Nombre de usuario para iniciar sesión.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|user_password|Contraseña encriptada del usuario.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|user_email|Dirección de correo electrónico del usuario.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|user_phone|Número de teléfono del usuario.|No|No|Sí|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|user_is_admin|Indica si el usuario es Administrador (1) o normal (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_User_user_is_admin|||No|No|False|No|No|||
|user_is_active|Indica si el usuario está activo (1) o inactivo (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_User_user_is_active|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_User|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_User_Email|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_User_Username|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[User](
	[id_user] [bigint] IDENTITY(1,1) NOT NULL,
	[user_username] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[user_password] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[user_email] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[user_phone] [nvarchar](255) COLLATE Latin1_General_CS_AS NULL,
	[user_is_admin] [bit] NOT NULL,
	[user_is_active] [bit] NOT NULL,
 CONSTRAINT [PK_User] PRIMARY KEY CLUSTERED 
(
	[id_user] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_User_Email] UNIQUE NONCLUSTERED 
(
	[user_email] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_User_Username] UNIQUE NONCLUSTERED 
(
	[user_username] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
ALTER TABLE [dbo].[User] ADD  CONSTRAINT [DF_User_user_is_admin]  DEFAULT ((0)) FOR [user_is_admin]
GO
ALTER TABLE [dbo].[User] ADD  CONSTRAINT [DF_User_user_is_active]  DEFAULT ((1)) FOR [user_is_active]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para el usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'COLUMN',@level2name=N'id_user'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre de usuario para iniciar sesión.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'COLUMN',@level2name=N'user_username'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Contraseña encriptada del usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'COLUMN',@level2name=N'user_password'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Dirección de correo electrónico del usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'COLUMN',@level2name=N'user_email'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Número de teléfono del usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'COLUMN',@level2name=N'user_phone'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si el usuario es Administrador (1) o normal (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'COLUMN',@level2name=N'user_is_admin'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el usuario no se crea como Administrador (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'CONSTRAINT',@level2name=N'DF_User_user_is_admin'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si el usuario está activo (1) o inactivo (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'COLUMN',@level2name=N'user_is_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el usuario se crea como activo (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'CONSTRAINT',@level2name=N'DF_User_user_is_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'CONSTRAINT',@level2name=N'PK_User'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para la dirección de correo electrónico del usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'CONSTRAINT',@level2name=N'UQ_User_Email'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para el nombre de usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User', @level2type=N'CONSTRAINT',@level2name=N'UQ_User_Username'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Un usuario representa una persona que interactúa con el sistema,
con sus credenciales y datos básicos de acceso.

¿Para qué sirve?:

1. Gestión de acceso y autenticación en el sistema.

2. Almacenamiento de información básica de los usuarios.

3. Control de estados y permisos de usuarios.

4. Seguimiento de actividad y auditoría de usuarios.

5. Base para la personalización de la experiencia de usuario.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'User'
GO
~~~


## Usada Por

[dbo.UserCompany](https://github.com/JamesEspitia/SERP/wiki/dbo.UserCompany)


## Depende De


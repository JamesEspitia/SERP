## Descripción

Una compañía representa una entidad empresarial con sus datos de identificación,
ubicación y características principales dentro del sistema ERP.

¿Para qué sirve?:

1. Gestión centralizada de la información básica de las empresas en el sistema.

2. Soporte para operaciones comerciales y administrativas específicas de cada empresa.

3. Cumplimiento de requisitos legales y fiscales relacionados con la identificación empresarial.

4. Base para la configuración de parámetros y políticas específicas de cada empresa.

5. Facilitar la gestión multi-empresa dentro del sistema ERP.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T19:50:52.903|
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
|id_compa|Identificador único para la compañía.|Sí|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|compa_name|Nombre legal completo de la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_tradename|Nombre comercial o marca de la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_doctype|Tipo de documento de identificación de la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|2|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_docnum|Número de identificación fiscal o documento legal de la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_address|Dirección física de la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_city|Ciudad donde está ubicada la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_state|Departamento o estado donde está ubicada la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_country|País donde está ubicada la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_industry|Sector industrial al que pertenece la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_phone|Número de teléfono principal de la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_email|Dirección de correo electrónico principal de la compañía.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_website|Sitio web oficial de la compañía.|No|No|Sí|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_logo|Logo oficial de la compañía.|No|No|Sí|No|0|0|nvarchar|sys|nvarchar|-1|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|compa_active|Indica si la compañía está activa (1) o inactiva (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_Company_compa_active|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_Company|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Company](
	[id_compa] [bigint] IDENTITY(1,1) NOT NULL,
	[compa_name] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_tradename] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_doctype] [nvarchar](2) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_docnum] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_address] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_city] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_state] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_country] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_industry] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_phone] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_email] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[compa_website] [nvarchar](255) COLLATE Latin1_General_CS_AS NULL,
	[compa_logo] [nvarchar](max) COLLATE Latin1_General_CS_AS NULL,
	[compa_active] [bit] NOT NULL,
 CONSTRAINT [PK_Company] PRIMARY KEY CLUSTERED 
(
	[id_compa] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
ALTER TABLE [dbo].[Company] ADD  CONSTRAINT [DF_Company_compa_active]  DEFAULT ((1)) FOR [compa_active]
GO
ALTER TABLE [dbo].[Company]  WITH CHECK ADD  CONSTRAINT [CK_Company_DocType] CHECK  (([compa_doctype]='OT' OR [compa_doctype]='PP' OR [compa_doctype]='CE' OR [compa_doctype]='CC' OR [compa_doctype]='NI'))
GO
ALTER TABLE [dbo].[Company] CHECK CONSTRAINT [CK_Company_DocType]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'id_compa'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre legal completo de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_name'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre comercial o marca de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_tradename'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Tipo de documento de identificación de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_doctype'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Número de identificación fiscal o documento legal de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_docnum'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Dirección física de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_address'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Ciudad donde está ubicada la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_city'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Departamento o estado donde está ubicada la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_state'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'País donde está ubicada la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_country'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Sector industrial al que pertenece la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_industry'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Número de teléfono principal de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_phone'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Dirección de correo electrónico principal de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_email'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Sitio web oficial de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_website'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Logo oficial de la compañía.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_logo'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si la compañía está activa (1) o inactiva (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'COLUMN',@level2name=N'compa_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto la compañía se crea como activa (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'CONSTRAINT',@level2name=N'DF_Company_compa_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'CONSTRAINT',@level2name=N'PK_Company'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Una compañía representa una entidad empresarial con sus datos de identificación,
ubicación y características principales dentro del sistema ERP.

¿Para qué sirve?:

1. Gestión centralizada de la información básica de las empresas en el sistema.

2. Soporte para operaciones comerciales y administrativas específicas de cada empresa.

3. Cumplimiento de requisitos legales y fiscales relacionados con la identificación empresarial.

4. Base para la configuración de parámetros y políticas específicas de cada empresa.

5. Facilitar la gestión multi-empresa dentro del sistema ERP.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Validación del tipo de documento permitido para la compañía (NI, CC, CE, PP, OT).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'Company', @level2type=N'CONSTRAINT',@level2name=N'CK_Company_DocType'
GO
~~~


## Usada Por

[dbo.BranchOffice](https://github.com/JamesEspitia/SERP/wiki/dbo.BranchOffice)

[dbo.Company](https://github.com/JamesEspitia/SERP/wiki/dbo.Company)

[dbo.CostCenter](https://github.com/JamesEspitia/SERP/wiki/dbo.CostCenter)

[dbo.Role](https://github.com/JamesEspitia/SERP/wiki/dbo.Role)

[dbo.UserCompany](https://github.com/JamesEspitia/SERP/wiki/dbo.UserCompany)


## Depende De


## Descripción

Una sucursal representa un establecimiento físico o punto de operación 
que pertenece a una compañía específica.

¿Para qué sirve?:

1. Gestión y control de múltiples ubicaciones de una misma empresa.

2. Organización de operaciones por punto de venta o servicio.

3. Seguimiento y análisis de desempeño por sucursal.

4. Asignación y control de recursos específicos por ubicación.

5. Facilitar la gestión descentralizada de operaciones empresariales.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T19:50:52.923|
|Última Modificación|2024-12-05T19:50:52.923|
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
|id_broff|Identificador único para la sucursal.|Sí|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|company_id|Compañía a la que pertenece esta sucursal.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|broff_name|Nombre descriptivo de la sucursal.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_code|Código único que identifica la sucursal dentro de la empresa.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_address|Dirección física de la sucursal.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_city|Ciudad donde está ubicada la sucursal.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_state|Departamento o estado donde está ubicada la sucursal.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_country|País donde está ubicada la sucursal.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_phone|Número de teléfono de la sucursal.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_email|Dirección de correo electrónico de la sucursal.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|broff_active|Indica si la sucursal está activa (1) o inactiva (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_BranchOffice_broff_active|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_BranchOffice|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_Company_BranchCode|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[BranchOffice](
	[id_broff] [bigint] IDENTITY(1,1) NOT NULL,
	[company_id] [bigint] NOT NULL,
	[broff_name] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_code] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_address] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_city] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_state] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_country] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_phone] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_email] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[broff_active] [bit] NOT NULL,
 CONSTRAINT [PK_BranchOffice] PRIMARY KEY CLUSTERED 
(
	[id_broff] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_Company_BranchCode] UNIQUE NONCLUSTERED 
(
	[company_id] ASC,
	[broff_code] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY]
GO
ALTER TABLE [dbo].[BranchOffice] ADD  CONSTRAINT [DF_BranchOffice_broff_active]  DEFAULT ((1)) FOR [broff_active]
GO
ALTER TABLE [dbo].[BranchOffice]  WITH CHECK ADD  CONSTRAINT [FK_BranchOffice_Company] FOREIGN KEY([company_id])
REFERENCES [dbo].[Company] ([id_compa])
GO
ALTER TABLE [dbo].[BranchOffice] CHECK CONSTRAINT [FK_BranchOffice_Company]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'id_broff'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Compañía a la que pertenece esta sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'company_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre descriptivo de la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_name'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Código único que identifica la sucursal dentro de la empresa.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_code'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Dirección física de la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_address'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Ciudad donde está ubicada la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_city'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Departamento o estado donde está ubicada la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_state'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'País donde está ubicada la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_country'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Número de teléfono de la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_phone'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Dirección de correo electrónico de la sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_email'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si la sucursal está activa (1) o inactiva (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'COLUMN',@level2name=N'broff_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto la sucursal se crea como activa (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'CONSTRAINT',@level2name=N'DF_BranchOffice_broff_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'CONSTRAINT',@level2name=N'PK_BranchOffice'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para la combinación de ID de compañía y código de sucursal.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'CONSTRAINT',@level2name=N'UQ_Company_BranchCode'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Una sucursal representa un establecimiento físico o punto de operación 
que pertenece a una compañía específica.

¿Para qué sirve?:

1. Gestión y control de múltiples ubicaciones de una misma empresa.

2. Organización de operaciones por punto de venta o servicio.

3. Seguimiento y análisis de desempeño por sucursal.

4. Asignación y control de recursos específicos por ubicación.

5. Facilitar la gestión descentralizada de operaciones empresariales.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia a la compañía en la tabla Company.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'BranchOffice', @level2type=N'CONSTRAINT',@level2name=N'FK_BranchOffice_Company'
GO
~~~


## Usada Por


## Depende De

[dbo.Company](https://github.com/JamesEspitia/SERP/wiki/dbo.Company)


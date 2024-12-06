## Descripción

Un centro de costo representa una unidad organizacional dentro de una empresa
que permite agrupar y controlar costos específicos.

¿Para qué sirve?:

1. Gestión y control de costos por unidad organizativa.

2. Seguimiento detallado de gastos y presupuestos por área.

3. Análisis de rentabilidad por centro de responsabilidad.

4. Facilitación de la toma de decisiones basada en costos.

5. Implementación de estructuras jerárquicas para el control de costos.

## Propiedades

|Propiedad|Valor|
|---------|-----|
|Fecha De Creación|2024-12-05T20:10:09.580|
|Última Modificación|2024-12-05T20:10:09.580|
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
|id_cosce|Identificador único para el centro de costo.|Sí|No|No|Sí|1|1|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|company_id|Compañía a la que pertenece este centro de costo.|No|Sí|No|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|cosce_parent_id|Centro de costo superior en la jerarquía organizativa.|No|Sí|Sí|No|0|0|bigint|sys|bigint|8|19|0||No|No|No||No||||||No|No|False|No|No|||
|cosce_code|Código único que identifica el centro de costo.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|cosce_name|Nombre descriptivo del centro de costo.|No|No|No|No|0|0|nvarchar|sys|nvarchar|255|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|cosce_description|Descripción detallada del centro de costo y su propósito.|No|No|Sí|No|0|0|nvarchar|sys|nvarchar|-1|0|0|Latin1_General_CS_AS|No|Sí|No||No||||||No|No|False|No|No|||
|cosce_budget|Presupuesto asignado al centro de costo.|No|No|No|No|0|0|decimal|sys|decimal|9|15|2||No|No|No||No|||DF_CostCenter_cosce_budget|||No|No|False|No|No|||
|cosce_level|Nivel en la jerarquía de centros de costo (1 para nivel superior).|No|No|No|No|0|0|smallint|sys|smallint|2|5|0||No|No|No||No|||DF_CostCenter_cosce_level|||No|No|False|No|No|||
|cosce_active|Indica si el centro de costo está activo (1) o inactivo (0).|No|No|No|No|0|0|bit|sys|bit|1|1|0||No|No|No||No|||DF_CostCenter_cosce_active|||No|No|False|No|No|||

## Índices

|Nombre|Nombre Automático|Deshabilitado|Llave Primaria|Tipo|Grupo De Archivos|Único|Pertenece A Una Restricción|Ignorar Llaves Duplicadas|Admite Bloqueos De Página|Admite Bloqueos De Fila|Factor De Llenado|Texto Completo|Objeto Del Sistema|Llenar Índice|No Recalcular|Particionado|Esquema De Partición|XML|Padre XML|Tipo De Índice XML Secundario|
|------|-----------------|-------------|--------------|----|-----------------|-----|---------------------------|-------------------------|-------------------------|-----------------------|-----------------|--------------|------------------|-------------|-------------|------------|--------------------|---|---------|-----------------------------|
|PK_CostCenter|No|No|Sí|CLUSTERED|PRIMARY|Sí|No|No|Sí|Sí|0|No|No|No|No|No||No||0|
|UQ_Company_CostCenterCode|No|No|No|NONCLUSTERED|PRIMARY|Sí|Sí|No|Sí|Sí|0|No|No|No|No|No||No||0|

## Comando SQL

~~~sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[CostCenter](
	[id_cosce] [bigint] IDENTITY(1,1) NOT NULL,
	[company_id] [bigint] NOT NULL,
	[cosce_parent_id] [bigint] NULL,
	[cosce_code] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[cosce_name] [nvarchar](255) COLLATE Latin1_General_CS_AS NOT NULL,
	[cosce_description] [nvarchar](max) COLLATE Latin1_General_CS_AS NULL,
	[cosce_budget] [decimal](15, 2) NOT NULL,
	[cosce_level] [smallint] NOT NULL,
	[cosce_active] [bit] NOT NULL,
 CONSTRAINT [PK_CostCenter] PRIMARY KEY CLUSTERED 
(
	[id_cosce] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY],
 CONSTRAINT [UQ_Company_CostCenterCode] UNIQUE NONCLUSTERED 
(
	[company_id] ASC,
	[cosce_code] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON, OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF) ON [PRIMARY]
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
GO
ALTER TABLE [dbo].[CostCenter] ADD  CONSTRAINT [DF_CostCenter_cosce_budget]  DEFAULT ((0)) FOR [cosce_budget]
GO
ALTER TABLE [dbo].[CostCenter] ADD  CONSTRAINT [DF_CostCenter_cosce_level]  DEFAULT ((1)) FOR [cosce_level]
GO
ALTER TABLE [dbo].[CostCenter] ADD  CONSTRAINT [DF_CostCenter_cosce_active]  DEFAULT ((1)) FOR [cosce_active]
GO
ALTER TABLE [dbo].[CostCenter]  WITH CHECK ADD  CONSTRAINT [FK_CostCenter_Company] FOREIGN KEY([company_id])
REFERENCES [dbo].[Company] ([id_compa])
GO
ALTER TABLE [dbo].[CostCenter] CHECK CONSTRAINT [FK_CostCenter_Company]
GO
ALTER TABLE [dbo].[CostCenter]  WITH CHECK ADD  CONSTRAINT [FK_CostCenter_Parent] FOREIGN KEY([cosce_parent_id])
REFERENCES [dbo].[CostCenter] ([id_cosce])
GO
ALTER TABLE [dbo].[CostCenter] CHECK CONSTRAINT [FK_CostCenter_Parent]
GO
ALTER TABLE [dbo].[CostCenter]  WITH CHECK ADD  CONSTRAINT [CK_CostCenter_Level] CHECK  (([cosce_level]>(0)))
GO
ALTER TABLE [dbo].[CostCenter] CHECK CONSTRAINT [CK_CostCenter_Level]
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Identificador único para el centro de costo.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'id_cosce'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Compañía a la que pertenece este centro de costo.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'company_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Centro de costo superior en la jerarquía organizativa.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'cosce_parent_id'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Código único que identifica el centro de costo.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'cosce_code'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nombre descriptivo del centro de costo.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'cosce_name'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Descripción detallada del centro de costo y su propósito.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'cosce_description'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Presupuesto asignado al centro de costo.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'cosce_budget'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el presupuesto asignado al centro de costo es cero.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'DF_CostCenter_cosce_budget'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Nivel en la jerarquía de centros de costo (1 para nivel superior).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'cosce_level'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el nivel en la jerarquía de centros de costo es 1, es decir, de nivel superior.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'DF_CostCenter_cosce_level'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Indica si el centro de costo está activo (1) o inactivo (0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'COLUMN',@level2name=N'cosce_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Por defecto el centro de costo se crea como activo (1).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'DF_CostCenter_cosce_active'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave primaria de la tabla' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'PK_CostCenter'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Restricción única para la combinación de ID de compañía y código de centro de costo.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'UQ_Company_CostCenterCode'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Un centro de costo representa una unidad organizacional dentro de una empresa
que permite agrupar y controlar costos específicos.

¿Para qué sirve?:

1. Gestión y control de costos por unidad organizativa.

2. Seguimiento detallado de gastos y presupuestos por área.

3. Análisis de rentabilidad por centro de responsabilidad.

4. Facilitación de la toma de decisiones basada en costos.

5. Implementación de estructuras jerárquicas para el control de costos.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia a la compañía en la tabla Company.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'FK_CostCenter_Company'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Llave foránea que referencia al centro de costo superior en la tabla CostCenter.' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'FK_CostCenter_Parent'
GO
EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'Validación del nivel jerárquico del centro de costo (debe ser mayor a 0).' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'CostCenter', @level2type=N'CONSTRAINT',@level2name=N'CK_CostCenter_Level'
GO
~~~


## Usada Por

[dbo.CostCenter](https://github.com/JamesEspitia/SERP/wiki/dbo.CostCenter)

[dbo.CostCenter](https://github.com/JamesEspitia/SERP/wiki/dbo.CostCenter)


## Depende De

[dbo.Company](https://github.com/JamesEspitia/SERP/wiki/dbo.Company)

[dbo.CostCenter](https://github.com/JamesEspitia/SERP/wiki/dbo.CostCenter)


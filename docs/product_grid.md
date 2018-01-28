Customize Akeneo 2.1 product grid
=======================

NOTE: This document contains information collected during the fast investigation
so some points might be implemented in more convenient way and/or according to initial platform overhead. 
According to this, the information below will be updated after a more deep investigation.

This article describes how permanently change default columns set for product grid and contains general 'side' overview 
of grid concept, which might be enough for further customizations.

Main configuration file for product grid is `src/Pim/Bundle/EnrichBundle/Resources/config/datagrid/product.yml`.
In this file you should customize columns section, by adding your custom attributes.
E.g :
```yml
columns:
        ...
        custom_attribute_code:
            label: Custom Attribute
            data_name:     custom_attribute_code
            type:          field
        ...
```

@TODO ...


Now, we need to redeclare default 
[ProductDatasource](https://github.com/akeneo/pim-community-dev/blob/2.1/src/Pim/Bundle/DataGridBundle/Datasource/ProductDatasource.php#L126)
and use our own, because we want to change `$defaultNormalizedItem` by adding to list of properties our `custom_attribute_code`.

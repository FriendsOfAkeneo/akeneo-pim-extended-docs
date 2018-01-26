Customize Akeneo 2.1 product grid
=======================

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

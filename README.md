# SilverStripe GridField Groupable

This module allows drag & drop grouping of items in a GridField. 
It bolts on top of- and depends on GridFieldOrderableRows for the drag & drop sorting functionality

### Screenshot

![image](https://cloud.githubusercontent.com/assets/1005986/15631519/677fd806-256e-11e6-83a3-d4c072211d1b.png)
Example application (Block Enhancements module): assign content blocks to block-areas by drag & drop
```

## Installation

#### Composer

	composer require micschk/silverstripe-groupable-gridfield

### Requirements (all pulled in by composer)

* SilverStripe CMS ~3.1
* SilverStripe GridFieldExtensions

## Usage:
```php
$grid = new GridField(
    'ExampleGrid',
    'Example Grid',
    $this->Items(),
    $gfConfig = GridFieldConfig::create()
        ->addComponent(new GridFieldToolbarHeader())
        ->addComponent(new GridFieldTitleHeader())
        ->addComponent(new GridFieldEditableColumns())
        ->addComponent(new GridFieldOrderableRows())
        ->addComponent(new GridFieldFooter())
);
// add Groupable (example from BlockEnhancements module)
$gfConfig->addComponent(new GridFieldGroupable(
        'BlockArea',    // The fieldname to set the Group
        'Area',   // A description of the function of the group
        'none',         // A title/header for items without a group/unassigned
        array(          // List of available values for the Group field
            'BeforeContent' => 'Before Content',
            'AfterContent' => 'Before Content',
        )
    ));

## Thank you

[TITLE WEB SOLUTIONS](http://title.dk/) for sponsoring the isolation of this module out of [Blocks Enhancements](https://github.com/micschk/silverstripe-block_enhancements)

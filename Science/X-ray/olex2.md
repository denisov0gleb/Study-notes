# Olex2 #

Created 16.09.20 by **DGL**

Modified 17.09.20 by **DGL**

[Olex2 site](https://www.olexsys.org/)


# Table of Content:


<!-- vim-markdown-toc GFM -->

1. [Usage](#usage)
1. [CIF](#cif)
1. [Commands](#commands)
	1. [Bonding information](#bonding-information)
	1. [Molecule growing](#molecule-growing)
	1. [Names, labels](#names-labels)
	1. [Atom selection](#atom-selection)
	1. [Cell and symmetry](#cell-and-symmetry)
1. [Images](#images)
1. [Keybindings](#keybindings)

<!-- vim-markdown-toc -->

## Usage ##
[Table of Content](#table-of-content)

Open *.res*, *.ins*, *.cif* files.


## CIF ##
[Table of Content](#table-of-content)

`twin` - search for twinning in centrosymentrical groups.

`basf 0.5` - **???**

`isor value` - **???**

`fvar` - link two or more atoms through a free variable (usually the chemical occupancy for different parts).

`omit -4 value` - omit any reflections with 2theta more than **value**.


## Commands ##
[Table of Content](#table-of-content)

### Bonding information ###

`htab` - generate *.lst* file with main information + the D...A distance in the end (not
included in *cif* file).

`pipi` - print the distance between centers of the aromatic rings (centroid-to-centroid distance).

`esd` - print the distance between two selected atoms, including the error.


### Molecule growing ###

`pack #` - change packing parameter

`compaq` - moves all atoms or fragments of the asymmetric unit as close to each other as possible.


### Names, labels ###

`name type` - rename selected to the *type*

`name type1 type2` - rename *type1* to *type2*

`name -s=suffix` - rename selected suffixes.

`Legend` - show/hide legend

`labels` - show/hide labels

`labels -p` - show/hide parts

`showp value` - show only requested parts


### Atom selection ###

`envi r-2.7 atom` - print a list of atoms within a sphere of radius **r** around the atom (named or selected).

`-h` - including hydrogens

`-q` - including Q-peaks


### Cell and symmetry ###

`cell` - show/hide cell


## Images ##
[Table of Content](#table-of-content)

`save model name` - generate *.oxm* (*name.oxm*) file for image storage


## Keybindings ##
[Table of Content](#table-of-content)

**\<F3\>** - show/hide labels

**Ctrl+R** - refine structure

**Ctrl+H** - toggle between show H, show H with internal h-bonds, hide H.

**Ctrl+T** - toggle between show structure only, structure + text, only text.


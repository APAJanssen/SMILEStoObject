# SMILEStoObject
*PyMOL plugin to convert SMILES to molecules*

PyMOL is amazingly flexible software to visualize biomolecules. It even comes with a built-in molecular builder that allows you to mold molecules out of thin air. This builder is not really user friendly though, and a better way to introduce (small) molecules to PyMOL is desired if one wants to use it for docking. 
## SMILES
Daylight's [Simplified Molecular-input Line-Entry Specification](https://en.wikipedia.org/wiki/Simplified_molecular-input_line-entry_system), or SMILES, is a decades old 'language' to express a molecular structure (graph) in a single line of quasi-human readable symbols. SMILES for many drugs and other important molecules can be found on Wikipedia or PubChem. Structure sketchers such as ChemDraw and the [PubChem Sketcher](https://pubchem.ncbi.nlm.nih.gov//edit3/index.html) also allow you to generate SMILES of any structure.
Although somewhat human readable (with practice), PyMOL definitely has no clue how to interpret these. This plugin changes this.
## Under the hood
The plugin requires the installation of [RDKit](https://www.rdkit.org), an extremely useful Python module. It uses the chemical intelligence of this module to translate SMILES to a mol-block, which *can* be interpreted by PyMOL. But this isn't all it does. RDKit is also used to generate 1 or more 3D conformers before pushing the data to PyMOL. We live in a 3D world after all.
Finally, the plugin also contains functionality (and the code) of [Dimorphite-DL](https://git.durrantlab.pitt.edu/jdurrant/dimorphite_dl), a product of the [Durrant lab](https://durrantlab.pitt.edu/). This allows the user to specify a pH-range for which the model will predict protonation states. For more information on this, see Ropp PJ, Kaminsky JC, Yablonski S, Durrant JD (2019) *J Cheminform* 11:14. doi:10.1186/s13321-019-0336-9. 
Protonation states can also be made explicit in the SMILES, and is thus optional. 

## Setting it up
As mentioned, we'll need to install RDKit. Depending on how you've installed PyMOL, it either uses the system Python interpreter, or something like `conda`.
For the system interpreter, just launch a terminal. For `conda`, launch the appropriate prompt on Windows or just a terminal on Linux. Then give the command:
`pip install rdkit`
After installation, just download the .zip from [GitHub](https://github.com/APAJanssen/SMILEStoObject). Use the Plugin manager in PyMOL to install the plugin. 
Enjoy!

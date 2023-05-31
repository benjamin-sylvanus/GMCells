# Docs





<figure><img src="../../.gitbook/assets/Blank diagram.svg" alt=""><figcaption><p>User Pipeline</p></figcaption></figure>



All simulations are run via our executable. The executable takes arguments from the initial invocation. If there aren't enough parameters passed as command line arguments the program prompts the user to fix the required values.&#x20;

This was designed so we can create shell scripts to chain calls of our executable with varying parameters.&#x20;

The GUI provides a simple way configure parameters and preprocess cells. It uses config.json files while creating batch configurations. When we run simulations from the GUI the config.json is converted to a list of commands for each cell and is functionally the same as a shell script.&#x20;

The GUI enables you to reload previous configurations or export shell scripts for future use. We made sure the API/CLI was compatible with our GUI so users can switch between them at their convenience.






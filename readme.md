# Hux
Hux is a WYSIAWYG ("What You See Is (Almost) What You Get") terminal script editor for [Aleph One](https://alephone.lhowon.org/), developed using [Qt](https://www.qt.io/). The GUI allows users to create, edit, and preview terminals in any AO-compatible scenario, with controls provided for image and text alignment, formatting, etc. 

All necessary operations can be done through the tool, minimizing the risk of errors caused by incorrect syntax, and reducing the time cost of creating/editing terminals.

The app was developed using Qt version 5.12.9, but it should be compatible with newer versions.

_NOTE: Hux provides a close, but not 1:1 representation of Aleph One's terminal rendering. All scripting content is preserved, but there can be small differences in the displayed result (e.g line wrapping)_

Hux es una WYSIAWYG (del inglés "What You See Is What You Get", que significa "lo que se ve es lo que se obtiene") editor de script de terminal para [Aleph One](https://alephone.lhowon.org/), desarrollado usando [Qt](https://www.qt.io/). La GUI permite a los usuarios crear, editar, previsualizar cualquier escenario compatible con AO (AlephOne), con controles para la alineación de imágenes y texto, forma, etc.

Todas las operaciones necesarias pueden realizarse atreves de la herramienta, minimizando el riesgo causado por una sintaxis incorrecta y reduciendo el costo de tiempo para la creación y edición de terminales.

La app fue desarrollada usando Qt versión 5.12.9, pero debería ser compatible con las versiones más nuevas.

_NOTA: Hux proporciona una representación cercana, pero no 1:1 de la representación de la terminal de Aleph One. Se conserva todo el contenido del scripteado, pero puede haber pequeñas diferencias en el resultado mostrado (por ejemplo, ajustes de líneas)_

## Getting started

Once you open Hux, you must first either [import](#importing-scenarios) a scenario from a split folder, or [load](#loading-scenarios) a Hux scenario file.

## Empezando

Una vez que abra Hux, primero debes [importar](#importing-scenarios) un escenario desde la carpeta dividida (split folder), or [abrir](#loading-scenarios) un archivo de escenario Hux.

### Importing scenarios

Hux can make use of split folders generated by [Atque](https://sourceforge.net/projects/igniferroque/) to load the terminal data.

To import a scenario from a split folder, simply click _File -> Import Scenario Scripts_ and select the root directory of a split scenario generated by Atque. The scenario browser will display all the levels that have valid terminal script files.

 When you start work on a new scenario, or want to edit an existing scenario that has no Hux-specific data, you must create a split folder and import it, after which you can [add levels](#editing-scenarios) that require terminal data.

*NOTE: make sure the split folder also has a valid "Resources" folder!*

### Importando escenarios

Hux puede hacer uso de carpetas divididas generadas por [Atque](https://sourceforge.net/projects/igniferroque/) para cargar la información de la terminal.

Para importar un escenario desde una carpeta dividida (split folder), simpemente haga click en _File -> Import Scernacio Scrips_ y seleccione el directorio raíz de un escenario dividido generado por Atque. El navegador de escenario mostrará en pantalla todos los niveles que tengan un archivo script válido.

 Cuando comienza a trabajar en un nuevo escenario, o desea editar un escenario que no tiene datos específicos de Hux, debe crear una carpeta dividida (split folder) e importarla, después de esto puede [agregar niveles](#editing-scenarios) que requieran datos de terminal.

*NOTA: ¡Asegúrese de que la carpeta dividida también tenga una carpeta "Resources" (Recursos) válida!*

### Loading scenarios

Hux uses a custom file to save/load terminal scripts (using JSON). 
The file is read and written by the application, no manual editing is necessary (except when merging changes, e.g via a diff tool).


To load a Hux scenario file, click _File -> Load Scenario_ and select a valid scenario JSON file.

The custom file is recommended for developers who work on terminals, since it allows them to store additional metadata and can more easily merge changes between multiple users.

*NOTE: Hux expects the scenario file to be in the same directory as the "Resources" folder for the same scenario, otherwise it cannot load the images referenced in the scripts!*

### Cargando escenarios

Hux usa un archivo personalizado para guardar/cargar script de terminal (usando JSON). 
Este archivo es leido y escrito por la aplicación, no es necesaria una edición manual (excepto cuando se combinan cambios, ejemplo vía herramientas de diferencias)

Para cargar un archivo de escenario Hux, click _File -> Load Scenario_ y seleccione un archivo JSON válido de escenario.

El archivo personalizado se recomienda para los desarrolladores que trabajan en terminales, ya que les permite almacenar metadatos adicionales y puede fusionar más fácilmente los cambios entre varios usuarios.

*NOTA: Hux espera que los archivos del escenario estén en el mismo directorio que la carpeta "Resources" apra el mismo escenario; de lo contrario, no podrá cargar las imágenes a las que se hace referencia en los scripts.*

### Main window

This is the main window that is first displayed when the app is loaded. 

The left side of the window shows the [Scenario Browser](#scenario-browser) and an information table for the currently selected terminal. 

The right side shows a [Screen Browser](#screen-browser) for the selected terminal, a table containing information about the currently selected screen, and a terminal preview display.

### Ventana principal

Esta es la ventana principal que se muestra por primera vez cuando se carga la aplicación.

El lado izquierdo de la ventana muestra el [Navegador de Escenarios](#scenario-browser) y una tabla de información para la terminal actualmente seleccionada.

El lado derecho muestra un [Navegador de Pantalla](#screen-browser) para el terminal seleccionado, una tabla que contiene información sobre la pantalla seleccionada actualmente y una vista previa de la terminal.

#### Scenario Browser

Each level in the scenario is represented by a folder in the list view. 

Double-clicking a level will list the terminals contained within said level. 

Clicking on a terminal will show its contents in the [Screen Browser](#screen-browser). To return to the main scenario view, use the "up" button above the *Scenario Browser*.

#### Navegador de Escenarios

Cada nivel en el escenario está representado por una carpeta en la vista de lista.

Hacer doble click en un nivel, aparecerá una lista de las terminales contenidos en dicho nivel.

Al hacer clic en un termina, se mostrará su contenido en el [Explorador de Pantalla](#screen-browser). Para volver a la vista principal del escenario, utilice el botón "Up" (Arriba) sobre el *Explorador de Escenarios*

#### Screen Browser

Every terminal's screens are split into the "UNFINISHED" and "FINISHED" sections. 

Clicking on any screen item will show its information and render its preview on the display. 

The buttons under the display can also be used to navigate between the selected terminal's screens.

#### Explorador de Pantallas

Las pantallas de cada terminal se dividen en las secciones "UNFINISHED" (Sin terminar) y "FINISHED" (Terminada)

Al hacer clic en cualquier elemento de la pantalla, se mostrará su información y aparecerá una vista previa en la pantalla.

Lo botones debajo de la pantalla también se pueden usar para navegar entre las pantalla del terminal seleccionado.

### Editing scenarios

The [Scenario Browser](#scenario-browser) lets you edit the scenario contents, including both levels and their terminals.

- Add and remove is done via the buttons under the [Scenario Browser](#scenario-browser) view.
- Levels can be edited via right-clicking and selecting "Edit Level". This opens the [Level Editor](#level-editor) dialog.
- You can use drag & drop to reorder levels and terminals. Changing the level order does not affect the export, it is only for user convenience.
  - *NOTE: changing terminal order will change the terminal IDs in the exported script. This can invalidate references in the map data!*
- Double-clicking a level opens it and displays a list of its terminals.
- Terminals can be copy & pasted within and between levels. To copy selected terminals, right-click and select "Copy", then right-click again in the desired location and select "Paste".
- Double-clicking a terminal in the [Scenario Browser](#scenario-browser) opens a [Terminal Editor](#terminal-editor) window, which allows users to edit the terminal contents.

### Editando escenarios

El [Explorado de Escenarios](#scenario-browser) te permite editar el contenido del escenario, incluidos los niveles y sus terminales.

- Agregar y eliminar se realiza a través de los botones debajo de la vista [Navegador de Escenarios](#scenario-browser).
- Los niveles se puede editar haciendo click derecho y seleccionando "Edit Level" (Editar Nivel) [Editor de Nivel](#level-editor).
- Puede arrastrar y soltar para reordenar niveles y terminales. Cambiar el orden de los niveles no afercta a la exportación, es solo para conveniencia del usuario.
  - *NOTA: cambiando el orden de las terminales cambiará el ID  de los terminales en el script exportado. Esto puede invalidad las referencias en los datos del mapa!*
- al hacer doble click en un nivel, se abre y muestra una lista de sus terminales.
- Las terminales se puede copiar y pegar dentro y entre los niveles. Para copiar los terminales seleccionados, haga click derecho y selecciones "Copy", y luego haga click derecho nuevamente en la ubicación deseada y selecciones "Paste".
- Al hacer doble click en un terminal en el [Navegador de Escenarios](#scenario-browser) abre una ventana del [Editor de Terminales](#terminal-editor), que permite a los usuarios editar el contenido de la terminal.

### Level Editor

This dialog allows you to modify the level attributes. You can edit the level name, the script file name, and the level folder name.

The level name is for user convenience only. Its display name in-game needs to be set up in the relevant scripts outside of Hux.

When adding a new level or reorganizing the scenario, you must be provide the correct folder and script file names. This allows Hux to overwrite the appropriate files when exporting the scenario.

*NOTE: the current implementation excludes characters from folder and file names that are not allowed in the Windows file system!*

### Editor de Nivel

Esta ventana permite modificar los atributos del nivel. Puede editar el nombre del nivel, el nombre del archivo de script y el nombre de la carpeta de nivel.

El nombre del nivel es solo para comodidad del usuario. Su nombre para mostrar en el juego debe configurarse en los scripts relevantes fuera de Hux.

Al agregar un nuevo nivel o reorganizar el escenario, debe proporcionar la carpeta y los nombres de los script correctos. Esto le permite a Hux sobrescribir los archivos apropiados al exporta el escenario.

*NOTA: ¡la implementación actual excluye caracteres de carpetas y nombres de archivos que no están permitidos en el sistema de archivos de Windows!*

### Terminal Editor

When you double-click a terminal in the [Scenario Browser](#scenario-browser), it opens a [Terminal Editor](#terminal-editor) window for this terminal.

The left side of the window shows controls for editing terminal attributes (i.e teleport info) and the [Screen Browser](#screen-browser), which can be used to view and modify the screens within the terminal. 

The right side contains an editor view where the screen contents and metadata can be edited, along with a preview display for the currently edited screen.

- You can give terminals a custom name to identify them more easily. This data is Hux-specific, it does not get exported with the terminal script files.
- The [Screen Browser](#screen-browser) contains two folders, corresponding to the "UNFINISHED" and "FINISHED" screen groups. Double-click a folder to view and edit its contents.
- Editing the screen list is similar to editing levels in the [Scenario Browser](#scenario-browser):
  - Add or remove screens using the buttons below the browser.
  - Move screens using drag & drop.
  - Copy & paste selected screens by right-clicking and selecting the appropriate action.
- To edit a screen, select it in the [Screen Browser](#screen-browser). This will update the screen editor view and the preview display. Switching screens will save changes to the last selected screen.
- Once you are done editing, you can close the window using "OK". This will apply the changes to the terminal in the [Scenario Browser](#scenario-browser).

### Terminal Editor

Cuando hace click en una terminal en el [Navegador de Escenario](#scenario-browser), se abre una ventana del [Editor de Terminal](#terminal-editor) para este terminal.

El lado izquierda de la ventana muestra los controles para editar los atributos de la terminal (e.j. información de teletransportacion) y el [Explorador de Pantalla](#screen-browser), que se puede usar para ver y modificar las pantalla dentro de la terminal. 

El lado derecho contiene una vista de editor donde se puede editar los contenidos de la pantalla y los metadatos, junto con un vista previa de la pantalla editada actualmente.

- Puede dar a los terminales un nombre personalizado que para identificarlos fácilmente. Estos datos son específicos de Hux, no se exportan con los archivos de script del terminal.
- El [Explorador de Pantallas](#screen-browser) contienen dos carpetas, correspondiente a los grupos de pantalla "UNFINISHE" y "FINISHED". Haga doble click en una carpeta para ver y editar su contenido.
- La edición de la lista de pantallas es similar a la edición de niveles ene el [Navegador de Escenarios](#scenario-browser):
  - Agregar o eliminar pantalla usando los botones debajo den navegador.
  - Mover pantallas usando arrastrar y soltar.
  - Copiar y pegar pantallas seleccionadas click derecho y seleccionando la acción apropiada.
- Para editar una pantalla, selecciónela en el [Screen Browser](#screen-browser). Esto actualizará la vista del editor de pantalla y la vista previa. AL cambiar de pantalla, se guardarán los cambios en la última pantalla seleccionada.
- Una vez que haya terminado de editar, puede cerrar la ventana usando "OK". Esto aplicara los cambiaos al terminal en el [Navegador de Escenario](#scenario-browser).

### Editing screens

When a screen is selected in the [Screen Browser](#screen-browser), the editor view will be updated with its contents, and the preview for the screen will be shown in the display. 

Any changes made to the screen contents will automatically update the preview.

The page also shows line numbers to help keep track of how close the text content is to the line limit.

If a screen's text content exceeds the line limit for a single page, the preview display will show a page counter. The counter's value corresponds to the (estimated) number of pages into which the engine will break up the text.

- Previews for the page breaking is currently not yet implemented. It's recommended that you do not let the text exceed the line limit, as this allows for less precise control over the text layout.
- For more details on the syntax and terminal scripting logic, consult the Marathon Infinity manual.

### Pantalla de edición

Cuando se selecciona una pantalla en el [Explorador de Pantalla](#screen-browser), la vista del editor se actualizará con su contenido y la vista previa de la pantalla se mostrará en la pantalla.

Cualquier cambio realizado en el contenido de la pantalla actualizará automáticamente la vista previa.

La página también muestra números de línea para ayudar a realizar un seguimiento de qué tan cerca está el contenido del texto del límite de línea.

Si el contenido de texto de una pantalla excede el límite de línea para una sola página, la pantalla de vista previa mostrará un contador de página. El valor del contador corresponde al número (estimado) de páginas en las que el motor dividirá el texto.

- Las vistas previas para el salto de página aun no están implementadas. Se recomienda que no permia que el texto exceda el límite de línea, ya que esto permite un control menos preciso sobre el diseño del texto.

- Para obtener más detalles sobre la sintaxis y la lógica de secuencias de comandos del terminal, consulte el manual de Marathon Infinity.

### Saving scenarios

If you have unsaved changes, you can save the scenario file using _File->Save Scenario_. This will save the terminal scripting data to the Hux-specific JSON file.

When saving for the first time, you will be prompted for a scenario name and location. Subsequent saves will overwrite this file. To save the scenario to a different location, you can use _File->Save Scenario As_.

*NOTE: editor-specific data (e.g terminal names) are only saved in the JSON file. This data is lost if the user tries to reload a scenario from the exported .txt files!*

The user can also be prompted to save when exiting (this will skip the above steps).

*NOTE: the application expects the scenario file to be in the same folder as the Resources folder for the scenario, otherwise it cannot access the referenced images!*

### Grabando escenarios

Si tiene cambios sin guardar, puede guardar el archivo de escenario utilizando _File -> Export Scenario Scripts_, Esto guardará los datos de la secuencia de comandos del terminal en el archivo JSON específico de Hux.

Al guardar por primera vez, se le pedirá un nombre y una ubicación para el escenario. Los guardados subsiguientes sobrescribirán este archivo. Para guardar el escenario en una ubicación diferente, puede usar _File->Save Scenario As_.

*NOTA: ¡los datos específicos del editor (por ejemplo, los nombres de terminales) solo se guardan en el archivo JSON. ¡Estos datos se pierden si el usuarios intenta volver a cargar un escenarios desde los archivos .txt exportados!*

También se le puede solicitar al usuario que guarde al salir (esto omitirá los pasos anteriores).

*NOTA: la aplicación espera que el archivo del escenario esté en la misma carpeta que la carpeta de Resources (Recursos) para el escenario; de lo contrario, ¡no podrá acceder a las imágenes a las que se hace referencia!*

### Exporting scenarios

In order to test the terminal changes in Aleph One, the terminal scripts have to be exported to a split folder, then merged using Atque.

To export a scenario, click _File -> Export Scenario Scripts_, which opens the export dialog. This will list all the levels and allows the user to preview the script contents. Clicking a level in the list will display the generated Aleph One terminal script.

Clicking OK will prompt the user to select a destination folder. This can be an existing split folder, in which case Hux will overwrite any existing terminal scripts. If no matching script is found for a level, Hux will create a new folder and script file.

*NOTE: make sure to adjust the level attributes so Hux overwrites the correct files in the correct folders!*

### Exportando escenarios

Para probar los cambios de la terminal en Aleph One, los scripts de terminal deben exportarse a una carpeta dividida y luego fusionarse con Atque.

Para exportar un escenario, haga click en _File -> Export Scenario Scripts_, que abre un cuadro de diálogo de exportación. Esto mostrará una lista de todos los niveles y le permitirá al usuario obtener una vista previa del contenido del script. Al hacer click en un nivel de la lista, se mostrará el script de terminal Aleph One generado.

Al hacer click en OK, se le pedirá al usuario que seleccione una carpeta de destino. Esta puede ser una carpeta dividida (split folder) existente, en cuyo caso Hux sobrescribirá cualquier script de terminal existente. Si no se encuentra un script coincidente para un nivel, Hux creara una nueva carpeta y un archivo sript.

*NOTA: ¡asegúrese de ajustar los atributos de nivel para que Hux sobrescriba los archivos correctos en las carpetas correctas!*

## License

See [LICENSE](https://github.com/janos-ijgyarto/HuxQt/blob/master/LICENSE) file.

## Licencia

Vea el archivo de [LICENCIA](https://github.com/janos-ijgyarto/HuxQt/blob/master/LICENSE).

## Useful links

- TODO: a link to the relevant manual for AO terminal scripting (e.g the Infinity manual)

## Links útiles

- PORHACER: un enlace al manual correspondiente para secuencia de comandos de terminal AO (por ejemplo, el manual de Infinity)
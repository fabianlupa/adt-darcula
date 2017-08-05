# adt-darcula
Darcula theme for ABAP Development Tools (ADT)

![Screenshot](https://blogs.sap.com/wp-content/uploads/2017/07/oxygen.png)

## WIP
Things to change in the settings:
- General
  - Appearance
    - Colors and Fonts
      - ABAP
  - Editors
    - Text Editors
      - Annotations
- ABAP Development
  - Editors
    - Source Code Editors
      - ABAP Keyword Colors -> This dialog has a separate import/export functionality

Configuration files:
- $WORKSPACE/.metadata/.plugins/com.genuitec.eclipse.ui.common.platform/color-definitions-fix.css generated file?
- $WORKSPACE/.metadata/.plugins/org.eclipse.core.runtime/.settings seems to contain all individual settings files

Tracked workspace file changes on configuration change:
- Changing `General -> Appearance -> Colors and Fonts -> ABAP -> Syntax Coloring -> Comment`
  - $WORKSPACE/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.eclipse.ui.workbench.prefs
    ```diff
    diff --git a/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.eclipse.ui.workbench.prefs b/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.eclipse.ui.workbench.prefs
    index aa3dc02..3c99e4d 100644
    --- a/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.eclipse.ui.workbench.prefs
    +++ b/.metadata/.plugins/org.eclipse.core.runtime/.settings/org.eclipse.ui.workbench.prefs
    @@ -1,3 +1,6 @@
     //org.eclipse.ui.commands/state/org.eclipse.ui.navigator.resources.nested.changeProjectPresentation/org.eclipse.ui.commands.radioState=false
    +ColorsAndFontsPreferencePage.expandedCategories=Tcom.sap.adt.ui.presentation\tTcom.sap.adt.tools.abapsource.ui.syntaxHighlight
    +ColorsAndFontsPreferencePage.selectedElement=Ccom.sap.adt.tools.abapsource.ui.comment
     PLUGINS_NOT_ACTIVATED_ON_STARTUP=;org.eclipse.m2e.discovery;
    +com.sap.adt.tools.abapsource.ui.comment=64,128,128
     eclipse.preferences.version=1
     ```
   - Changes here seem to override the "native" dark theme handling (which might be hard coded to the theme name?)

Export / Import:
- `File -> Export -> Preferences` exports all eclipse settings

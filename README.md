# LiferayNavigationMenuFragment

Ce fragment Liferay implémente un menu de navigation latéral dynamique basé sur la structure du site.
Il supporte les niveaux hiérarchiques, les icônes configurables, et un mode édition spécifique pour le Fragment Editor.

Le rendu est entièrement réalisé en FreeMarker (FTL) et s’appuie sur les objets de navigation fournis par Liferay (navItems, branchNavItems).

⚙️ Fonctionnalités

📂 Navigation hiérarchique (menu parent / sous-menu)

🔄 Détection automatique de la page active

🖊️ Support du Edit Mode Liferay

🖼️ Icônes configurables via :

lfr-editable (images éditables depuis le Fragment Editor)

Mapping dynamique (iconMapping)

♿ Accessibilité :

aria-haspopup

aria-expanded

🧩 Structure HTML propre et extensible

🧩 Variables principales
Variable	Description
displayDepth	Profondeur d’affichage de la navigation
navItems	Liste principale des éléments de navigation
branchNavItems	Branche active de navigation
isEditMode	Détection du mode édition (layoutMode == "edit")
iconMapping	Mapping dynamique page → icône
🧠 Logique FreeMarker

Conversion sécurisée des valeurs de configuration (?number)

Vérification de la présence des sous-niveaux (getChildren())

Ajout dynamique de classes CSS (active, edit-mode)

Gestion des icônes par nom de page

🖼️ Gestion des icônes

Chaque élément de menu peut contenir une icône éditable via :

<lfr-editable id="icon-${navItem.getName()}" type="image">
	<img src="...">
</lfr-editable>


Cela permet aux éditeurs de contenu de modifier les icônes directement depuis l’interface Liferay, sans code.

# repo-test-Azure-board

> **Repositorio de prueba** para la integración con Azure Boards (cuenta personal). No usar en producción.

Repo destino de las ramas que crea el workflow de
[`test-create-branch`](https://github.com/diego-caicedo14/test-create-branch) a partir de un issue.
Cada rama creada queda vinculada a un work item de Azure Boards (`diegocaicedo46/test-oxxo`).

## Ruleset: "Nomenclatura de ramas (tipo-folio-mvp-CHG)"

Cuenta personal sin GitHub Enterprise: no hay regex (`branch_name_pattern`), así que se usa **Restrict creations**
con excepciones por patrón (fnmatch). Solo se pueden crear ramas que coincidan con:

`feature-*-mvp*-CHG*`, `bugfix-*-mvp*-CHG*`, `hotfix-*-mvp*-CHG*`, `wip-*-mvp*-CHG*`, `cherryp-*-mvp*-CHG*`, `revert-*-mvp*-CHG*`
(además de `main`, `staging` y `develop`).

Es menos estricto que la regex de BUS-BackOffice (no valida dígitos ni largo del folio/CHG), pero alcanza para la prueba.
En una org con GitHub Enterprise se usa la regex de `BO_Pipelines/utils/regex-rules.json → branch-nomenclatures`.

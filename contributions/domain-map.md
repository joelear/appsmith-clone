# Proposed Domains

- App Builder (dom.app-builder) — Visual low‑code editor: canvas, widgets, property pane, layout systems.
  - Evidence: app/client/src/pages/Editor/**, layoutSystems/anvil/**, actions/widgetSelectionActions.ts, Canvas.tsx, PropertyPane/**

- App Runtime (dom.app-runtime) — End‑user app viewing and runtime rendering.
  - Evidence: app/client/src/pages/AppViewer/**

- Data Platform (dom.data-platform) — Datasources, queries/actions, API/SaaS editors, plugin execution.
  - Evidence: app/client/src/pages/Editor/APIEditor/**, DataSourceEditor/**, QueryEditor/**, SaaSEditor/**, src/api/ActionAPI.tsx, sagas/DatasourcesSagas.ts, sagas/ActionExecution/PluginActionSaga.ts, entities/Datasource/**

- Admin (dom.admin) — Workspace/org settings, members, authentication providers, audit logs, embed settings, upgrades.
  - Evidence: app/client/src/pages/Settings/**, src/pages/workspace/** (Invite/Members), ce/ee/pages/AdminSettings/**, ce/ee/pages/Applications/*Embed* , ce/ee/pages/Auditlogs/**

- Version Control (dom.vcs-sync) — Git sync, import/export, environments.
  - Evidence: app/client/src/pages/Editor/gitSync/**, client/packages/dsl/**, server/**/git/**, server/**/import/**, server/**/export/**, server/**/*Git*.java, server/**/*Environment*

- Widgets & Design System (dom.widgets) — Widget library, widget blocks, and design system components.
  - Evidence: app/client/src/widgets/**, src/components/propertyControls/**, client/packages/design-system/**, packages/icons/**, packages/storybook/**

- AI Agents (dom.ai-agents) — Agentic AI features across FE and BE, chat and tooling integration.
  - Evidence: client/packages/rts/src/chat/**, client/widgets/wds/**, client/generators/**, server/**/appsmith-ai/**, server/**/ai/**, appsmith-plugins/appsmithAiPlugin/**

- Evaluation Engine (dom.evaluation) — Data tree, JS/expression evaluation, workers, linting.
  - Evidence: client/src/ce/entities/DataTree/**, DependencyMap/**, entities/workers/**, sagas/EvaluationsSaga.ts, EvalWorkerActionSagas.ts, LintingSagas.ts, PostEvaluationSags.ts

## Review Notes
- Builder vs Widgets: Some widget‑creation logic lives in builder sagas (e.g., WidgetAddition/Deletion/Operation Sagas). Keep widgets (design system + widget catalogue) separate from builder (editor flows), but expect touchpoints.
- Server sources aren’t fully present in this fork; CODEOWNERS references indicate server‑side modules for Git, Import/Export, AI. Domain placement is based on these references.
- Admin overlaps with Identity/Access (invites, members). If auth providers and SSO config emerge in code, consider splitting into Identity & Admin.

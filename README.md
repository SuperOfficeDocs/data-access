# data-access

This repo is now **inactive** and will be marked as archived once issues have been migrated.

The contents has moved to make it easier for collaboraters to located and work with SuperOffice documentation.

This content now live and breath in the [superoffice-docs](https://github.com/SuperOfficeDocs/superoffice-docs) repo. 

This following is a list of actions and migration points of what was moved where. 

1. data-access/docs/ > superoffice-docs/docs/api/
1. Delete welcome.md
1. Replace toc.yml with 00-custom/toc.yml. Remove ../ prefixes.
1. whats-new/ > superoffice-docs/release-notes/api/. Move the corresponding items from toc.yml to superoffice-docs/release-notes/toc.yml
1. Delete default-index.md and req-*.md from includes/
1. Move folder expander-data-exchange to service.
1. Move person/* to contact/howto/.
1. Move contact/* to company/howto/.
1. Move diary/* to diary/howto/.
1. Move documents/* to document/howto/. Except for plugins to plugin folder. See step 22
1. Move project/* to project/howto/.
1. Move sales/* to sale/howto/.
1. Update tocs to reflect the above moves.
1. Move assets/downloads/* to superoffice-docs/docs/assets/downloads/api/*. assets/downloads.md > assets/downloads/api/index.md
1. custom-fields/overview.md > custom-objects/udef/index.md. Move subfolders of custom-fields to custom-entities/udef/howto/ (See crmscript step for completion)
1. Rename getting-started > overview (for consistentcy)
1. netserver/index.md > overview/netserver.md
1. Move remaining contents of netserver folder 1 level up.
1. Move contents of netserver/webhooks to automation/webhooks
1. Move netserver/preferences/preferences.md to cache/ TBD
1. Move netserver/preferences/get-set* to admin/user-preferences/howto/
1. Move netserver/erp-connectors and quote-connectors to plugins.
1. Move sentry plugin to plugin folder.

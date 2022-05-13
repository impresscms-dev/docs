---
description: >-
  The ImpressCMS core exposes some events to make it easier to hook into its
  functionality and adapt the way things work without having to hack the core
  itself
---

# Core events

The ImpressCMS core exposes some events to make it easier to hook into its functionality and adapt the way things work without having to hack the core itself. One of the easiest ways of using these events is in a preload.

A good example of using events with the preload functionality of ImpressCMS can be found in skenows blog post "[How I Added a New Preload to My Site](https://www.impresscms.org/modules/news/article.php?article\_id=960)"

| event name                                | event description                                                                                    |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| eventStartCoreBoot                        | the start of the core boot process, near the beginning of include/common.php                         |
| eventFinishCoreBoot                       | the end of the core boot process, near the end of include/common.php                                 |
| eventStartOutputInit                      | the end of the output init process, in header.php after instantiation of $icmsTpl                    |
| eventBeforeFooter                         | when footer.php is called, at the beginning of the file                                              |
| eventAdminHeader                          | output content in the ACP head                                                                       |
| eventAdminBeforeFooter                    | output content at the end of ACP head                                                                |
| eventBeforePreviewTarea                   | to be triggered when entering MyTextSanitizer::displayTarea() function                               |
| eventBeforeDisplayTarea                   | to be triggered when exiting MyTextSanitizer::displayTarea() function                                |
| eventBeforeDisplayHTMLarea                | to be triggered when entering icms\_HTMLPurifier::displayHTMLarea() function                         |
| eventAfterDisplayHTMLarea                 | to be triggered when exiting icms\_HTMLPurifier::displayHTMLarea() function                          |
| eventAfterFilterTextareaDisplay           | triggered after completing icms\_core\_DataFilter::filterTextareaDisplay() function                  |
| eventAfterFilterHTMLdisplay               | triggered after icms\_core\_DataFilter::filterHTMLdisplay() function                                 |
| eventBeforeFilterTextareaInput            | triggered before text from a textarea is processed to save to the database                           |
| eventAfterFilterTextareaInput             | triggered after text from a textarea is processed to save to the database                            |
| eventBeforeFilterHTMLinput                | triggered before text from a textarea is processed as HTML to save to the database                   |
| eventAfterFilterHTMLinput                 | triggered after text from a textarea is processed as HTML to save to the database                    |
| eventBeforeFilterHTMLdisplay              | triggered before text from a textarea is processed as HTML to display                                |
| eventAfterFilterHTMLdisplay               | triggered after text from a textarea is processed as HTML to display                                 |
| eventBeforeDisplayTarea                   | triggered before before text from a textarea is processed to display                                 |
| eventAfterDisplayTarea                    | triggered after text from a textarea is processed to display                                         |
| eventAfterPreviewTarea                    | triggered after text from a textarea is processed for preview                                        |
| eventSavingSystemAdminPreferencesItem     | triggered before saving preferences in the admin control panel (modules/system/preferences/main.php) |
| eventAfterSaveSystemAdminPreferencesItems | triggered after  saving preferences in the admin control panel (modules/system/preferences/main.php) |

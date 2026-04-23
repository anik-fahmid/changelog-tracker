=== ChangeScout ===
Contributors: anikfahmid
Tags: changelog, ai, email notifications, release notes, automation
Requires at least: 5.6
Tested up to: 6.9
Stable tag: 1.0.2
Requires PHP: 7.4
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

AI-powered changelog tracking that monitors plugin/service release pages and emails you summaries of what changed.

== Description ==

**ChangeScout** monitors changelog URLs (plugin pages, SaaS apps, documentation sites) and uses AI to generate plain-English summaries of what changed. Summaries are delivered to your inbox on your chosen schedule or on demand.

= Key Features =

* **Multi-URL tracking** — monitor multiple changelog pages simultaneously
* **AI summaries** — supports Google Gemini, OpenAI (GPT-4), and Anthropic Claude
* **Scheduled emails** — weekly, bi-weekly, or monthly delivery
* **Force send** — fetch and email latest changelogs on demand (independent from scheduled emails)
* **Change detection** — only emails when content actually changes (MD5 hash comparison)
* **Custom SMTP** — configure Gmail or any SMTP server for reliable delivery
* **Auto-detect** — automatically find changelog URLs from any domain
* **Dashboard widget** — quick-glance status from the WordPress admin dashboard

= External Services =

**Jina Reader (r.jina.ai)**
* Service: https://jina.ai
* Privacy Policy: https://jina.ai/legal/

**Google Gemini API**
* Service: https://ai.google.dev
* Terms: https://ai.google.dev/terms

**OpenAI API**
* Service: https://openai.com
* Privacy Policy: https://openai.com/policies/privacy-policy/

**Anthropic Claude API**
* Service: https://anthropic.com
* Privacy Policy: https://www.anthropic.com/privacy

== Installation ==

1. Upload the `changescout` folder to `/wp-content/plugins/`
2. Activate the plugin through the **Plugins** menu in WordPress
3. Navigate to **Settings > ChangeScout**
4. Enter your AI provider API key (Gemini, OpenAI, or Claude)
5. Add your changelog URLs to track
6. Configure your notification email and schedule

== Frequently Asked Questions ==

= Which AI providers are supported? =

Google Gemini (free tier available), OpenAI GPT-4, and Anthropic Claude. You need to provide your own API key for the chosen provider.

= How does change detection work? =

The plugin stores an MD5 hash of each changelog page's content. On each fetch, it compares the new hash with the stored one. If they differ, the page is summarised and included in the next email.

= Does the force-send button affect scheduled emails? =

No. Force-send is completely independent from scheduled emails. It bypasses the cache and sends immediately without updating the change-detection hash, so scheduled emails still fire normally.

= What is Jina Reader used for? =

Jina Reader (r.jina.ai) converts changelog web pages into clean markdown before they are sent to the AI provider. This improves summary quality and reduces token usage. The plugin sends only the URL to Jina Reader; Jina fetches the page and returns its text content.

= Can I use this without an AI provider API key? =

No. An API key for at least one supported provider is required to generate summaries.

= How do I set up Gmail SMTP? =

Enable 2-Factor Authentication on your Google account, then generate an App Password at myaccount.google.com/apppasswords. Use `smtp.gmail.com`, port `587`, encryption `TLS`, and enter your Gmail address and the App Password.

== Changelog ==

= 1.0.2 =
* Fixed the send time dropdown labels to display clean times like 8:00 AM

= 1.0.1 =
* Fixed settings fields that were not persisting correctly after save
* Fixed notification email field saving
* Fixed SMTP enable/disable setting persistence
* Fixed dashboard widget refresh behavior

= 1.0.0 =
* Initial release
* AI-powered changelog summaries with Gemini, OpenAI, and Claude
* Auto-detect changelog URLs from any domain
* SMTP configuration with test button
* Eye toggle for API key and password fields
* Force-fetch isolation from scheduled emails
* Content extraction via Jina Reader

== Upgrade Notice ==

= 1.0.2 =
Fixes the send time dropdown labels.

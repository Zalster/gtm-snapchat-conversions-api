*# Snapchat Conversions API Tag for Google Tag Manager (Server-side)*
Snapchat Conversions API Tag for Google Tag Manager (Server-side)

The Snapchat Conversions API is a Server-to-Server (S2S) integration that allows you to share website and app visitor events directly to Snapchat. Data that is shared via the Conversions API is processed similar to information shared via other Snapchat data integration business tools, like the Snapchat Pixel or Snapchat Offline Conversions etc

This Tag uses the standard GA4 Client and parses GA4 input into Snapchat data and sends it through the Conversions API.

/This tag also supports to send from other sources/

*## Input variables*
* Snapchat Pixel ID
* Snapchat Conversions API Token
* (optional) Custom Setup (if not using mapping)

*## GA4 Standard Events Mapping*
The Tag parses all GA4 Client Events into Snapchat Standard Events.  Inheriting data from the GA4 Client is only supported for (most) web events.

*### Mapped Events (GA4 => Snapchat)*

  `page_view - PAGE_VIEW`

  `view_item - VIEW_CONTENT`

  `view_item_list - LIST_VIEW`

  `search - SEARCH`

  `add_to_cart - ADD_CART`

  `add_to_wish_list - ADD_TO_WISH_LIST`

  `begin_checkout - START_CHECKOUT`

  `add_payment_info - ADD_BILLING`

  `login - LOGIN`

  `purchase - PURCHASE`

  `sign_up - SIGN_UP`

  `spend_virtual_currency - SPENT_CREDITS`

  `subscribe - SUBSCRIBE`

*## Other ways to use the Tag*
If you are not using GA4 standard events you can still use this tag to send through this Tag with a simple post request. The pixel id and related token will still be set up in Google Tag Manager.

The request Parameters supported are the following

`x-sc-app-id` - The Snap App ID associated with your app (a unique code generated in Ads Manager and included in your MMP dashboard). Required for app events.

`x-sc-snap-app-id` - The Snap App ID associated with your app (a unique code generated in Ads Manager and included in your MMP dashboard). Required for app events.

`x-sc-event-type` - Event type required for all web, app, and offline events. (PURCHASE, SAVE, START_CHECKOUT, ADD_CART, VIEW_CONTENT, ADD_BILLING, SIGN_UP, SEARCH, PAGE_VIEW, SUBSCRIBE, AD_CLICK, AD_VIEW, COMPLETE_TUTORIAL, INVITE, LOGIN, SHARE, RESERVE, ACHIEVEMENT_UNLOCKED, ADD_TO_WISHLIST, SPENT_CREDITS, RATE, START_TRIAL, LIST_VIEW, APP_INSTALL, APP_OPEN, CUSTOM_EVENT_1, CUSTOM_EVENT_2, CUSTOM_EVENT_3, CUSTOM_EVENT_4, CUSTOM_EVENT_5)

`x-sc-event-conversion-type` - Where the event took place. Required for all web, app, and offline events. Use the appropriate value accordingly (OFFLINE, WEB, MOBILE_APP)

`x-sc-event-tag`  - Custom event set label - ex (in-store, weekend sales, back-to-school campaign, etc). Required for all web, app, and offline events. May be used for future tagging and audience targeting.

`x-sc-timestamp` - The Epoch timestamp for the conversion happening. We can handle second level or millisecond level granularity. However, we do encourage requests to provide millisecond level granularity. Required for all web, app, and offline events. Please note: The timestamp cannot be more than 28 days in the past

`x-sc-email` - Plain text or Lowercase SHA256 hash of normalized email. Highly recommended for all web, app, and offline events when available. This tag will hash any plain text with SHA256.

 `x-sc-idfa or x-sc-aaid` - Plain text or Lowercase SHA256 hash of normalized MAID (IDFA or AAID). Recommended for all app events when available. This tag will hash any plain text with SHA256.

`x-scid` - If not using any subdomain with the cookie set you can send the scid as a parameter.  If you are using the Pixel SDK, you can access a cookie1 by looking at the _scid value.

`x-sc-idfv` - Plain text or Lowercase SHA256 hash of normalized IDFV. Highly recommended for app events. This tag will hash any plain text with SHA256.

`x-sc-phone-number` - Plain text or Lowercase SHA256 hash of normalized phone number. Highly recommended for all web, app, and offline events when available. This tag will hash any plain text with SHA256.

`x-sc-user-agent` - User agent of the device that was used. Recommended for all web and app events when available.

`x-sc-ip-address` - Plain text or SHA256 hash of the IP Address of the device (not server). We support IPv4 for web and app and IPv6 for web. Recommended for all web and app events when available.  This tag will hash any plain text with SHA256.

`x-sc-item-category` - Item or Category  - Example:
shoes
umbrellas
coats

`x-sc-item-ids` - International Article Number (EAN) when applicable, or other product or category identifier. This can be a single item ID, an array, or a list of item IDs to be separated by “,” or “;” 

`x-sc-description` - A string description for additional info - This is a free form text description with no specific format. Note: max 1024 characters

`x-sc-number-items` - number_items

`x-sc-price` - Value of the purchase. We allow list of prices to be separated with “,” or “;”

`x-sc-currency` - Standard ISO 4217 code - Supported Currencies: USD, AED, AUD, BGN, BRL, CAD, CHF, CLP, CNY, COP,CZK, DKK, EGP, EUR, GBP, GIP, HKD, HRK, HUF, IDR, ILS, INR, JPY, KRW, KWD, KZT, LBP, MXN, MYR, NGN, NOK, NZD, PEN, PHP, PKR, PLN, QAR,RON, RUB, SAR, SEK, SGD, THB, TRY, TWD, TZS, UAH, VND, ZAR, ALL, BHD, DZD, GHS, IQD, ISK, JOD, KES, MAD, OMR, XOF

`x-sc-transaction-id` - Transaction ID or order ID tied to the conversion event. This is an important field to include for deduplication

`x-sc-level` - Represents a level in the context of a game

`x-sc-client-dedup-id` - If you are reporting events via more than one method (Snap Pixel, App Ads Kit , Conversions API) you should use the same client_dedup_id across all methods, this will be used within a 48 hour scope of the first occurrence.

`x-sc-data-use` - For iOS 14.5 and above, users please indicate if we should treat the event as OPT_IN or OPT_OUT. For OPT_OUT user events, value is a list with only value of lmu 

Use value: [‘lmu’]

`x-sc-search-string` - The text that was searched for

`x-sc-page-url` - The URL of the web page where the event took place. Must include protocol (eg http, https)

`x-sc-sign-up-method` - A string indicating the sign up method.


*## Links*
[_Snapchat Conversions API_](https://marketingapi.snapchat.com/docs/conversion.html)

[_Google Tag Manager Server Side_](https://developers.google.com/tag-platform/tag-manager/server-side)

[_GA4 Send Data_](https://developers.google.com/tag-platform/tag-manager/server-side/send-data)


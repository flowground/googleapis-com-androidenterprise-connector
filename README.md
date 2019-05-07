# ![LOGO](logo.png) Google Play EMM **flow**ground Connector

## Description

A generated **flow**ground connector for the Google Play EMM API (version v1).

Generated from: https://api.apis.guru/v2/specs/googleapis.com/androidenterprise/v1/swagger.json<br/>
Generated at: 2019-05-07T17:41:10+03:00

## API Description

Manages the deployment of apps to Android for Work users.

## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Looks up an enterprise by domain name. This is only supported for enterprises created via the Google-initiated creation flow. Lookup of the id is not needed for enterprises created via the EMM-initiated flow since the EMM learns the enterprise ID in the callback specified in the Enterprises.generateSignupUrl call.

*Tags:* `enterprises`

#### Input Parameters
* `domain` - _required_ - The exact primary domain name of the enterprise to look up.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Acknowledges notifications that were received from Enterprises.PullNotificationSet to prevent subsequent calls from returning the same notifications.

*Tags:* `enterprises`

#### Input Parameters
* `notificationSetId` - _optional_ - The notification set ID as returned by Enterprises.PullNotificationSet. This must be provided.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Completes the signup flow, by specifying the Completion token and Enterprise token. This request must not be called multiple times for a given Enterprise Token.

*Tags:* `enterprises`

#### Input Parameters
* `completionToken` - _optional_ - The Completion token initially returned by GenerateSignupUrl.
* `enterpriseToken` - _optional_ - The Enterprise token appended to the Callback URL.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Enrolls an enterprise with the calling EMM.

*Tags:* `enterprises`

#### Input Parameters
* `token` - _required_ - The token provided by the enterprise to register the EMM.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Pulls and returns a notification set for the enterprises associated with the service account authenticated for the request. The notification set may be empty if no notification are pending.<br/>
> A notification set returned needs to be acknowledged within 20 seconds by calling Enterprises.AcknowledgeNotificationSet, unless the notification set is empty.<br/>
> Notifications that are not acknowledged within the 20 seconds will eventually be included again in the response to another PullNotificationSet request, and those that are never acknowledged will ultimately be deleted according to the Google Cloud Platform Pub/Sub system policy.<br/>
> Multiple requests might be performed concurrently to retrieve notifications, in which case the pending notifications (if any) will be split among each caller, if any are pending.<br/>
> If no notifications are present, an empty notification list is returned. Subsequent requests may return more notifications once they become available.

*Tags:* `enterprises`

#### Input Parameters
* `requestMode` - _optional_ - The request mode for pulling notifications.
Specifying waitForNotifications will cause the request to block and wait until one or more notifications are present, or return an empty notification list if no notifications are present after some time.
Speciying returnImmediately will cause the request to immediately return the pending notifications, or an empty list if no notifications are present.
If omitted, defaults to waitForNotifications.
    Possible values: returnImmediately, waitForNotifications.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Generates a sign-up URL.

*Tags:* `enterprises`

#### Input Parameters
* `callbackUrl` - _optional_ - The callback URL to which the Admin will be redirected after successfully creating an enterprise. Before redirecting there the system will add a single query parameter to this URL named "enterpriseToken" which will contain an opaque token to be used for the CompleteSignup request.
Beware that this means that the URL will be parsed, the parameter added and then a new URL formatted, i.e. there may be some minor formatting changes and, more importantly, the URL must be well-formed so that it can be parsed.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the name and domain of an enterprise.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Sets the account that will be used to authenticate to the API as the enterprise.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Deprecated and unused.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Returns a unique token to access an embeddable UI. To generate a web UI, pass the generated token into the managed Google Play javascript API. Each token may only be used to start one UI session. See the javascript API documentation for further information.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves IDs of all products for which the enterprise has a group license.

*Tags:* `grouplicenses`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of an enterprise's group license for a product.

*Tags:* `grouplicenses`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `groupLicenseId` - _required_ - The ID of the product the group license is for, e.g. "app:com.google.android.gm".
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the IDs of the users who have been granted entitlements under the license.

*Tags:* `grouplicenseusers`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `groupLicenseId` - _required_ - The ID of the product the group license is for, e.g. "app:com.google.android.gm".
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Finds approved products that match a query, or all approved products if there is no query.

*Tags:* `products`

#### Input Parameters
* `approved` - _optional_ - Specifies whether to search among all products (false) or among only products that have been approved (true). Only "true" is supported, and should be specified.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `language` - _optional_ - The BCP47 tag for the user's preferred language (e.g. "en-US", "de"). Results are returned in the language best matching the preferred language.
* `maxResults` - _optional_ - Specifies the maximum number of products that can be returned per request. If not specified, uses a default value of 100, which is also the maximum retrievable within a single response.
* `query` - _optional_ - The search query as typed in the Google Play store search box. If omitted, all approved apps will be returned (using the pagination parameters), including apps that are not available in the store (e.g. unpublished apps).
* `token` - _optional_ - A pagination token is contained in a request's response when there are more products. The token can be used in a subsequent request to obtain more products, and so forth. This parameter cannot be used in the initial request.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of a product for display to an enterprise admin.

*Tags:* `products`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `language` - _optional_ - The BCP47 tag for the user's preferred language (e.g. "en-US", "de").
* `productId` - _required_ - The ID of the product, e.g. "app:com.google.android.gm".
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the schema that defines the configurable properties for this product. All products have a schema, but this schema may be empty if no managed configurations have been defined. This schema can be used to populate a UI that allows an admin to configure the product. To apply a managed configuration based on the schema obtained using this API, see Managed Configurations through Play.

*Tags:* `products`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `language` - _optional_ - The BCP47 tag for the user's preferred language (e.g. "en-US", "de").
* `productId` - _required_ - The ID of the product.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Approves the specified product and the relevant app permissions, if any. The maximum number of products that you can approve per enterprise customer is 1,000.<br/>
> <br/>
> To learn how to use managed Google Play to design and create a store layout to display approved products to your users, see Store Layout Design.

*Tags:* `products`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `productId` - _required_ - The ID of the product.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Generates a URL that can be rendered in an iframe to display the permissions (if any) of a product. An enterprise admin must view these permissions and accept them on behalf of their organization in order to approve that product.<br/>
> <br/>
> Admins should accept the displayed permissions by interacting with a separate UI element in the EMM console, which in turn should trigger the use of this URL as the approvalUrlInfo.approvalUrl property in a Products.approve call to approve the product. This URL can only be used to display permissions for up to 1 day.

*Tags:* `products`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `languageCode` - _optional_ - The BCP 47 language code used for permission names and descriptions in the returned iframe, for instance "en-US".
* `productId` - _required_ - The ID of the product.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Lists all the managed configurations settings for the specified app. Only the ID and the name is set.

*Tags:* `managedconfigurationssettings`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `productId` - _required_ - The ID of the product for which the managed configurations settings applies to.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the Android app permissions required by this app.

*Tags:* `products`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `productId` - _required_ - The ID of the product.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Unapproves the specified product (and the relevant app permissions, if any)

*Tags:* `products`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `productId` - _required_ - The ID of the product.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Sends a test notification to validate the EMM integration with the Google Cloud Pub/Sub service for this enterprise.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Returns a service account and credentials. The service account can be bound to the enterprise by calling setAccount. The service account is unique to this enterprise and EMM, and will be deleted if the enterprise is unbound. The credentials contain private key data and are not stored server-side.<br/>
> <br/>
> This method can only be called after calling Enterprises.Enroll or Enterprises.CompleteSignup, and before Enterprises.SetAccount; at other times it will return an error.<br/>
> <br/>
> Subsequent calls after the first will generate a new, unique set of credentials, and invalidate the previously generated credentials.<br/>
> <br/>
> Once the service account is bound to the enterprise, it can be managed using the serviceAccountKeys resource.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `keyType` - _optional_ - The type of credential to return with the service account. Required.
    Possible values: googleCredentials, pkcs12.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Lists all active credentials for the service account associated with this enterprise. Only the ID and key type are returned. The calling service account must have been retrieved by calling Enterprises.GetServiceAccount and must have been set as the enterprise service account by calling Enterprises.SetAccount.

*Tags:* `serviceaccountkeys`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Generates new credentials for the service account associated with this enterprise. The calling service account must have been retrieved by calling Enterprises.GetServiceAccount and must have been set as the enterprise service account by calling Enterprises.SetAccount.<br/>
> <br/>
> Only the type of the key should be populated in the resource to be inserted.

*Tags:* `serviceaccountkeys`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Removes and invalidates the specified credentials for the service account associated with this enterprise. The calling service account must have been retrieved by calling Enterprises.GetServiceAccount and must have been set as the enterprise service account by calling Enterprises.SetAccount.

*Tags:* `serviceaccountkeys`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `keyId` - _required_ - The ID of the key.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Returns the store layout for the enterprise. If the store layout has not been set, returns "basic" as the store layout type and no homepage.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Sets the store layout for the enterprise. By default, storeLayoutType is set to "basic" and the basic store layout is enabled. The basic layout only contains apps approved by the admin, and that have been added to the available product set for a user (using the  setAvailableProductSet call). Apps on the page are sorted in order of their product ID value. If you create a custom store layout (by setting storeLayoutType = "custom" and setting a homepage), the basic store layout is disabled.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the details of all pages in the store.

*Tags:* `storelayoutpages`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Inserts a new store page.

*Tags:* `storelayoutpages`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Deletes a store page.

*Tags:* `storelayoutpages`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of a store page.

*Tags:* `storelayoutpages`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates the content of a store page. This method supports patch semantics.

*Tags:* `storelayoutpages`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates the content of a store page.

*Tags:* `storelayoutpages`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the details of all clusters on the specified page.

*Tags:* `storelayoutclusters`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Inserts a new cluster in a page.

*Tags:* `storelayoutclusters`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Deletes a cluster.

*Tags:* `storelayoutclusters`

#### Input Parameters
* `clusterId` - _required_ - The ID of the cluster.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of a cluster.

*Tags:* `storelayoutclusters`

#### Input Parameters
* `clusterId` - _required_ - The ID of the cluster.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates a cluster. This method supports patch semantics.

*Tags:* `storelayoutclusters`

#### Input Parameters
* `clusterId` - _required_ - The ID of the cluster.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates a cluster.

*Tags:* `storelayoutclusters`

#### Input Parameters
* `clusterId` - _required_ - The ID of the cluster.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `pageId` - _required_ - The ID of the page.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Unenrolls an enterprise from the calling EMM.

*Tags:* `enterprises`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Looks up a user by primary email address. This is only supported for Google-managed users. Lookup of the id is not needed for EMM-managed users because the id is already returned in the result of the Users.insert call.

*Tags:* `users`

#### Input Parameters
* `email` - _required_ - The exact primary email address of the user to look up.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Creates a new EMM-managed user.<br/>
> <br/>
> The Users resource passed in the body of the request should include an accountIdentifier and an accountType.<br/>
> If a corresponding user already exists with the same account identifier, the user will be updated with the resource. In this case only the displayName field can be changed.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Deleted an EMM-managed user.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves a user's details.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates the details of an EMM-managed user.<br/>
> <br/>
> Can be used with EMM-managed users only (not Google managed users). Pass the new details in the Users resource in the request body. Only the displayName field can be changed. Other fields must either be unset or have the currently active value. This method supports patch semantics.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates the details of an EMM-managed user.<br/>
> <br/>
> Can be used with EMM-managed users only (not Google managed users). Pass the new details in the Users resource in the request body. Only the displayName field can be changed. Other fields must either be unset or have the currently active value.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Generates an authentication token which the device policy client can use to provision the given EMM-managed user account on a device. The generated token is single-use and expires after a few minutes.<br/>
> <br/>
> You can provision a maximum of 10 devices per user.<br/>
> <br/>
> This call only works with EMM-managed accounts.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the set of products a user is entitled to access.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Modifies the set of products that a user is entitled to access (referred to as whitelisted products). Only products that are approved or products that were previously approved (products with revoked approval) can be whitelisted.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Revokes access to all devices currently provisioned to the user. The user will no longer be able to use the managed Play store on any of their managed devices.<br/>
> <br/>
> This call only works with EMM-managed accounts.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the IDs of all of a user's devices.

*Tags:* `devices`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the details of a device.

*Tags:* `devices`

#### Input Parameters
* `deviceId` - _required_ - The ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates the device policy. This method supports patch semantics.

*Tags:* `devices`

#### Input Parameters
* `deviceId` - _required_ - The ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `updateMask` - _optional_ - Mask that identifies which fields to update. If not set, all modifiable fields will be modified.

When set in a query parameter, this field should be specified as updateMask=<field1>,<field2>,...
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates the device policy

*Tags:* `devices`

#### Input Parameters
* `deviceId` - _required_ - The ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `updateMask` - _optional_ - Mask that identifies which fields to update. If not set, all modifiable fields will be modified.

When set in a query parameter, this field should be specified as updateMask=<field1>,<field2>,...
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the details of all apps installed on the specified device.

*Tags:* `installs`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Requests to remove an app from a device. A call to get or list will still show the app as installed on the device until it is actually removed.

*Tags:* `installs`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `installId` - _required_ - The ID of the product represented by the install, e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of an installation of an app on a device.

*Tags:* `installs`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `installId` - _required_ - The ID of the product represented by the install, e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Requests to install the latest version of an app to a device. If the app is already installed, then it is updated to the latest version if necessary. This method supports patch semantics.

*Tags:* `installs`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `installId` - _required_ - The ID of the product represented by the install, e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Requests to install the latest version of an app to a device. If the app is already installed, then it is updated to the latest version if necessary.

*Tags:* `installs`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `installId` - _required_ - The ID of the product represented by the install, e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Lists all the per-device managed configurations for the specified device. Only the ID is set.

*Tags:* `managedconfigurationsfordevice`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Removes a per-device managed configuration for an app for the specified device.

*Tags:* `managedconfigurationsfordevice`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForDeviceId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of a per-device managed configuration.

*Tags:* `managedconfigurationsfordevice`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForDeviceId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Adds or updates a per-device managed configuration for an app for the specified device. This method supports patch semantics.

*Tags:* `managedconfigurationsfordevice`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForDeviceId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Adds or updates a per-device managed configuration for an app for the specified device.

*Tags:* `managedconfigurationsfordevice`

#### Input Parameters
* `deviceId` - _required_ - The Android ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForDeviceId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves whether a device's access to Google services is enabled or disabled. The device state takes effect only if enforcing EMM policies on Android devices is enabled in the Google Admin Console. Otherwise, the device state is ignored and all devices are allowed access to Google services. This is only supported for Google-managed users.

*Tags:* `devices`

#### Input Parameters
* `deviceId` - _required_ - The ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Sets whether a device's access to Google services is enabled or disabled. The device state takes effect only if enforcing EMM policies on Android devices is enabled in the Google Admin Console. Otherwise, the device state is ignored and all devices are allowed access to Google services. This is only supported for Google-managed users.

*Tags:* `devices`

#### Input Parameters
* `deviceId` - _required_ - The ID of the device.
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Lists all entitlements for the specified user. Only the ID is set.

*Tags:* `entitlements`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Removes an entitlement to an app for a user.

*Tags:* `entitlements`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `entitlementId` - _required_ - The ID of the entitlement (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of an entitlement.

*Tags:* `entitlements`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `entitlementId` - _required_ - The ID of the entitlement (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Adds or updates an entitlement to an app for a user. This method supports patch semantics.

*Tags:* `entitlements`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `entitlementId` - _required_ - The ID of the entitlement (a product ID), e.g. "app:com.google.android.gm".
* `install` - _optional_ - Set to true to also install the product on all the user's devices where possible. Failure to install on one or more devices will not prevent this operation from returning successfully, as long as the entitlement was successfully assigned to the user.
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Adds or updates an entitlement to an app for a user.

*Tags:* `entitlements`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `entitlementId` - _required_ - The ID of the entitlement (a product ID), e.g. "app:com.google.android.gm".
* `install` - _optional_ - Set to true to also install the product on all the user's devices where possible. Failure to install on one or more devices will not prevent this operation from returning successfully, as long as the entitlement was successfully assigned to the user.
* `userId` - _required_ - The ID of the user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Lists all the per-user managed configurations for the specified user. Only the ID is set.

*Tags:* `managedconfigurationsforuser`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Removes a per-user managed configuration for an app for the specified user.

*Tags:* `managedconfigurationsforuser`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForUserId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of a per-user managed configuration for an app for the specified user.

*Tags:* `managedconfigurationsforuser`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForUserId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Adds or updates the managed configuration settings for an app for the specified user. If you support the Managed configurations iframe, you can apply managed configurations to a user by specifying an mcmId and its associated configuration variables (if any) in the request. Alternatively, all EMMs can apply managed configurations by passing a list of managed properties. This method supports patch semantics.

*Tags:* `managedconfigurationsforuser`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForUserId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Adds or updates the managed configuration settings for an app for the specified user. If you support the Managed configurations iframe, you can apply managed configurations to a user by specifying an mcmId and its associated configuration variables (if any) in the request. Alternatively, all EMMs can apply managed configurations by passing a list of managed properties.

*Tags:* `managedconfigurationsforuser`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `managedConfigurationForUserId` - _required_ - The ID of the managed configuration (a product ID), e.g. "app:com.google.android.gm".
* `userId` - _required_ - The ID of the user.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Revokes a previously generated token (activation code) for the user.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Generates a token (activation code) to allow this user to configure their managed account in the Android Setup Wizard. Revokes any previously generated token.<br/>
> <br/>
> This call only works with Google managed accounts.

*Tags:* `users`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `userId` - _required_ - The ID of the user.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves the details of all web apps for a given enterprise.

*Tags:* `webapps`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Creates a new web app for the enterprise.

*Tags:* `webapps`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Deletes an existing web app.

*Tags:* `webapps`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `webAppId` - _required_ - The ID of the web app.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Gets an existing web app.

*Tags:* `webapps`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `webAppId` - _required_ - The ID of the web app.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates an existing web app. This method supports patch semantics.

*Tags:* `webapps`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `webAppId` - _required_ - The ID of the web app.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Updates an existing web app.

*Tags:* `webapps`

#### Input Parameters
* `enterpriseId` - _required_ - The ID of the enterprise.
* `webAppId` - _required_ - The ID of the web app.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

### Retrieves details of an Android app permission for display to an enterprise admin.

*Tags:* `permissions`

#### Input Parameters
* `language` - _optional_ - The BCP47 tag for the user's preferred language (e.g. "en-US", "de")
* `permissionId` - _required_ - The ID of the permission.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - An opaque string that represents a user for quota purposes. Must not exceed 40 characters.
* `userIp` - _optional_ - Deprecated. Please use quotaUser instead.

## License

**flow**ground :- Telekom iPaaS / googleapis-com-androidenterprise-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.

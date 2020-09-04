# Instruktioner

## Skapa Azure AD App registration för Guacamole OpenID Connect
- https://portal.azure.com -> Azure Active Directory -> App registrations
- Redirect URI: https://<fqdn>/guacamole
- Notera Application ID och Directory (tenant) ID
- Aktivera ID tokens Implicit Grant: Authentication/Implicit grant/ID tokens

## Skapa Azure AD SDN för DNS-automation
- https://portal.azure.com -> Azure Active Directory -> App registrations
- Ingen Redirect URI
- Notera Application ID
- Skapa och notera en Client secret
- Tilldela DNS Zone Contributor Role assignment för DNS-zon

## Fyll i .env med korrekta uppgifter
- POSTGRES_PASSWORD - Ange änskat Postgres password
- GUAC_ADMIN - Fyll i full UPN (förnamn.efternamn@domän.tld) för önskat adminkonto
- GUAC_FQDN - FQDN för Guacamoleserver (publicly resolvable, kan vara privat IP)
- TENANT_ID - Directory (tenant) ID från app registration
- OPENID_CLIENT_ID - Application ID från Azure app registration för OIDC
- TLS_EMAIL - Emailadress för kontaktperson mot Let's Encrypt
- TLS_CLIENT_ID - Application ID från Azure app registration för DNS-automation
- TLS_CLIENT_SECRET - Client secret från Azure app registration för DNS-automation
- TLS_SUBSCRIPTION_ID - Subscription ID för DNS zon
- TLS_RESOURCE_GROUP - Namn på resursgrupp för DNS zon

## Starta
*docker-compose up -d*

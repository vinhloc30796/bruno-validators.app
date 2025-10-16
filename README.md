### Bruno collection for validators.app

This is a small Bruno collection I use to explore the `validators.app` API. It exists for my own convenience and learning. I do not claim ownership of the API, the data, or any related documentation.

- **Bruno docs**: https://docs.usebruno.com/
- **validators.app**: https://validators.app/
- **Solana's Discord** (see `#validator-dashboards` channel): https://discord.com/invite/solana

### Quick start

1) **Install Bruno** and open this folder as a collection.

2) **Create an Environment** (e.g. "Local") with variables:

- **baseUrl**: `https://www.validators.app/api/v1`
- **token**: `replace-me`
- **network**: one of `mainnet`, `testnet`, or `pythnet` (optional)
- (optional) **account**, **voteAccount**, etc., for requests that need them

3) **Auth header**: Requests include `Token: {{token}}` automatically (via collection/request headers). If a call returns 401, re-check the token.

### Useful requests in this collection

- **Server Ping**: `GET {{baseUrl}}/ping.json` → expects `{ "answer": "pong" }`
- **Validators List**: `GET {{baseUrl}}/validators/{{network}}.json`
- **Validator Details**: `GET {{baseUrl}}/validators/{{network}}/{{account}}.json`
- **Ping Times**: `GET {{baseUrl}}/ping-times/{{network}}.json`

Adjust query params like `limit`, `page`, and `order` as needed. All endpoints respond with JSON; you can swap `.json` for `.csv` if desired.

### Notes

- **Account required**: An API token from validators.app is required for most endpoints.
- **Rate limits**: The API enforces per-5-minute limits (varies by endpoint). If you see 429, wait for the reset.
- **Data types**: Some fields can be `null`. Active stake values are in lamports.

For full endpoint details, examples, and parameters, see the official docs on `https://validators.app/`.



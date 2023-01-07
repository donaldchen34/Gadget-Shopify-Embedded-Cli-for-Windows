### *** This is only meant for development ***

## To Start:
#### Open server
1. Open cmd and go to app directory
2. Run `yarn dev`
#### Open proxy
3. In separate cmd, Run `npx local-ssl-proxy --source 443 --target 3005`  


You still have to follow https://docs.gadget.dev/guides/tutorials/connecting-to-shopify#connect-to-an-embedded-shopify-cli-app. 
These are additional changes needed to get running on windows. 

The changes needed from the tutorial:
Change `shopify-cli-connection` from web/frontend/api.js to your client
Update package.json in web/frontend/api to use your client
Create connections between gadget and shopify (Look at tutorial)



## Changes:
### /web
index.js:
- Remove leading `/` from `STATIC_PATH`
- Remove extra `/`: Change `{__dirname}/frontend/` to `{__dirname}frontend/`

shopify.web.toml:
- Rename to `shopify.web.toml.backup`. 

### /web/frontend  
vite.config.js: 
- Change process.env.FRONTEND_PORT to a static port
- Remove proxy from server(proxy will be done manually)

package.json:
- Change dev command to only be `vite`


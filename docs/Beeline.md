---
stoplight-id: hbvjfa9pkwupt
---

# Beeline

This document is about integrating with beeline games

## API Flow

### [Get Header Enrichment](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_create)

This API used to check if the game is played within beeline network, if so the mobile number will be retrieved through the network. No need to fill the mobile number or the subscription step.

### [Create Session](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_create)

Beeline flow starts with creating game sessions. No need to send the identifier when the header enrichment enabled. The mobile number will be retrieved automatically.

### [Verify Session](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_verify)

This API will be used to verify the session mobile number. This step is not needed when the header enrichment is enabled.

### [Get Active Products Code](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_getActiveProductCodes)

This API will be used to get the current active product codes for the provided game and user.


### [Activate Session](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_activate)

This API used to activate the session using a product code. It will charge the customer if the product is not active.

### [Start Session](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_start)

This API used to mark the session in progress. After this point the session can accept score chunks.

### [Add Chunk](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_chunk)

This API is used to add score chunks to the session. These chunks will be used to caluclate the session score.

### [Finish Session](https://api.dev.gamiphy.co/games/api/#/Beeline/BeelineController_finish)

This API used to finish the session. It will calcualate the session score, calulcate the reward and add it to the user balance as (MB or Mins)
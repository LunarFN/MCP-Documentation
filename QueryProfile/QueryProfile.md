# Query Profile

### Queries the profile Athena, Common Core, Common Public aswell as the Stw Profiles if needed.

- Route: /api/game/v2/profile/:accountId/client/:command
- Method: POST
- Auth Required: Yes

#### To Ignore or let the MCP system run "empty" reutrn {}
#### Also at the Boot of the game Fortnite will send -1 as Revision as it does not know the revision of the profile yet.
#### After this Fortnite will send for example revision 10 to the server, this would mean that the server needs to return ProfileRevisionBase 10 and ProfileRevision 10 because on QueryProfile this will not change the MCP Revision of the Client as it only gets queried.

#### Common Public (Boot):
##### Client sends to server:
```
    Revision: -1
    Profile Id: common_public
```

#### Common Core (Boot):
##### Client sends to server:
```
    Revision: -1
    Profile Id: common_core
```

#### Athena (Boot):
##### Client sends to server:
```
    Revision: -1
    Profile Id: athena
```
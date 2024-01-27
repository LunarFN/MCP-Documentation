# EquipBattleRoyaleCustomization

### Sets items of Locker in Server database.

- Route: /api/game/v2/profile/:accountId/client/EquipBattleRoyaleCustomization
- Method: POST
- Auth Required: Yes

#### To Ignore or let the MCP system run "empty" reutrn {}

#### EquipBattleRoyaleCustomization (Boot):
##### Client sends to server:
**Query**
```
    Revision: 10
    Profile Id: athena
```
**Body**
```
{
	"slotName": "Character", // Name of Target in Locker
	"itemToSlot": "AthenaCharacter:CID_249_Athena_Commando_F_BlackWidow", // Skin
	"indexWithinSlot": 0, // Target in Locker
	"variantUpdates": []
}
```

##### Server sends to Client:
```
{
  "profileRevision": 11, // Revision +1 if updated succeded.
  "profileId": "athena", // only works on athena
  "profileChangesBaseRevision": 10, // Client Send
  "profileChanges": [
    {
      "changeType": "statModified", // Change Type fullProfileUpdate if Revision is not sync.
      "name": "favorite_character", // Target in Locker
      "value": "AthenaCharacter:CID_249_Athena_Commando_F_BlackWidow" // Skin
    }
  ],
  "profileCommandRevision": 10,
  "serverTime": "2024-01-27T11:41:31.674Z", // Data as ISO string format
  "responseVersion": 1
}
```
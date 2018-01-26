# camellia-core
Backend of version two of Camellia, an application for tea management

# Priorities
Our main priority is minimizing effort of use, which implies optimizing UI and speed.
- inventory management
- tasting notes (typed)
- tea history
- dashboard (tea tray)
  - timers
  - steep counts
  - selections (integrated with history)

# Technical Notes
### API Possibilities
- GraphQL
- Rest + json-api
- Inclusion of a type schema with all responses for easy use on the front end

### Tools
- FE: Typescript+Ember
- BE: either Typescript or Java

### Other considerations
- tag based organization

# Out of Scope
- community features (review, etc)
- custom tag types

# Future Work
- pictures
- tasting note visualizations
- tea volume/weight
- steep conditions (cold brew, etc)
- editing data


# Data Types and Flow
### Models
Teas
NameTag
  Label
LeafTags
  Label (inclusion in Enum)
RatingTags
  Score (inclusion in Enum)
TastingNoteTags
  Label
  Score (inclusion in Enum)
PriceTags
  Price
  Unit
SteepTimeTags
  SteepCount
  SteepTime
GenericTags
  Label
Tagging
  TagType (GenericTag, LeafTags, RatingTags, TastingNoteTags, PriceTags, SteepTimeTags, NameTag)
  TagId
  ModelType (Tea, Tasting, Brewing)
  ModelId
  PositionId
Tastings
  TeaId
  UserId
Brewings
  TeaId
  UserId
Ownerships
  TeaId
  InventoryId
REVIST ME PLEASEEEE!!!!! Events: # to search history for User, Tea, Inventory
  EventType (Tasting, Brewing, Ownerships, Inventories - on create)
  EventId
Inventories
  ManagerId # foreign key for users table
InventoryHoldings
  InventoryId
  UserId
Users
  Username (but its a valid email address)
  Password
  DisplayName
```
Example -
Users   |  InHoldings |  Inventories
Sarah   |  Mike/Work  |  Work
Mike    |  Cody/Work  |  Home
Cody    |  Mike/Home  |
        |  Sarah/Home |  
```





THIS IS THE ROUTE YOU MUST HIT:
http://localhost:8080/graphql/schema.json?query=%22apples%22

Overview

This document defines the standardized data schema used for all character cards in the game.

The schema converts character design data into a structured format readable by the game engine, removing dependency on spreadsheets during runtime.

All characters, troops, champions, buildings, spells, and spirits must follow this schema to ensure consistent gameplay behavior and data validation.

The schema is derived from the character stat spreadsheet used during design and balancing.


2. Core Identity Fields

These fields define the identity and classification of a character card.

Field	Type	Description
CardName	String	Name displayed in UI and gameplay
Type	Enum	Defines gameplay category
Faction	Enum	Mythological faction alignment
Rarity	Enum	Determines card rarity and progression
Type Options

Troop

Champion

Building

Spell

Spirit

Faction Options

Rakshasa

Vanara

Neutral

Rarity Options

Common

Rare

Epic

Hero

Example structure:

Identity
{
CardName: string
Type: enum
Faction: enum
Rarity: enum
}
3. Resource Cost Field

Defines the deployment cost of the card.

Field	Type	Description
Elixir	Integer	Resource cost required to deploy the card

Example:

ElixirCost: int
4. Core Combat Stats

These fields control the combat performance of characters.

Field	Type	Description
Health	Integer	Total hit points
Damage	Integer	Damage per attack
AttackCooldown	Float	Time between attacks
Range	Float	Attack distance

Example structure:

Stats
{
Health: int
Damage: int
AttackCooldown: float
Range: float
}
5. Karma System

Karma represents behavior alignment and combat tendencies derived from character personality.

Field	Type	Description
Karma	Enum	Defines combat attitude and AI tendencies
Karma Types
Karma Type	Behavior
Aggressive	Prioritizes attacking enemies
Defensive	Focuses on protection or structure defense
Disciplined	Balanced controlled combat behavior
Risk	High risk / high reward combat tendency

Example:

Karma
{
Alignment: Aggressive
}
6. Engine Flags

Engine flags track implementation status and technical integration.

Field	Type	Description
Model	String	Indicates asset status or model completion

Typical values:

done

pending

placeholder

Example:

EngineFlags
{
ModelStatus: done
}
7. Behavior Tags (AI Tags)

Behavior tags help define AI targeting priorities and battlefield behavior.

These tags are used by gameplay systems to determine how a unit acts in combat.

Tag	Behavior
Aggressive	Seeks enemies and engages quickly
Defensive	Protects structures or allies
Disciplined	Balanced targeting logic
Risk	Takes aggressive risks in combat

Example:

BehaviorTags
[
Aggressive
]
8. Example Character Data

Example card structured using the schema.

CardName: Rakshas Patra
Type: Troop
Faction: Rakshasa
Rarity: Common

Elixir: 2

Stats
{
Health: 400
Damage: 50
AttackCooldown: 1.2
Range: 1.5
}

Karma
{
Alignment: Aggressive
}

EngineFlags
{
ModelStatus: done
}

BehaviorTags
[
Aggressive
]
9. Supported Card Types

The system supports multiple card categories:

Category	Description
Troop	Standard battlefield units
Champion	High-impact hero characters
Building	Static defensive structures
Spell	Instant or temporary effects
Spirit	Small support entities
10. Data Validation Rules

To maintain consistency across characters, the following validation rules apply:

Every card must have CardName, Type, Faction, Rarity, and Elixir.

Combat units must include Health, Damage, AttackCooldown, and Range.

Each card must have exactly one Karma alignment.

Rarity must be within the supported rarity list.

Numerical values must remain within gameplay balancing ranges.

11. Implementation Notes

During development, characters are balanced using spreadsheets.

For runtime usage, the engine reads structured character data from Scriptable Objects or serialized data files.

This schema ensures all characters follow a consistent structure, improving maintainability and scalability.

12. Schema Summary
CharacterCard
 ├── Identity
 │   ├── CardName
 │   ├── Type
 │   ├── Faction
 │   └── Rarity
 │
 ├── ElixirCost
 │
 ├── Stats
 │   ├── Health
 │   ├── Damage
 │   ├── AttackCooldown
 │   └── Range
 │
 ├── Karma
 │
 ├── EngineFlags
 │
 └── BehaviorTags

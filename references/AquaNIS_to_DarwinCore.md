# Mapping of AquaNIS data to Darwin Core

The AquaNIS data can be seen as a taxonomic checklist in the context of the Darwin Core Standard. 
Check also the [Best Practices in Publishing Species Checklists](https://ipt.gbif.org/manual/en/ipt/latest/best-practices-checklists).

| AquaNIS term | Darwin Core term | Extension | Notes |
| --- | --- | --- | -- |
| `ID` | [`dwc:taxonID`](https://dwc.tdwg.org/terms/#dwc:taxonID) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | Identifier specific to the dataset. Recommended best practice is to use the internal original identifier where possible. |
| `Phylum` | [`dwc:phylum`](https://dwc.tdwg.org/terms/#dwc:phylum) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | |
| `Class` | [`dwc:class`](https://dwc.tdwg.org/terms/#dwc:class) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | |
| `Order` | [`dwc:order`](https://dwc.tdwg.org/terms/#dwc:order) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | |
| `Family` | [`dwc:family`](https://dwc.tdwg.org/terms/#dwc:family) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | |
| `Genus` | [`dwc:genus`](https://dwc.tdwg.org/terms/#dwc:genus) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | |
| `Species name` | [`dwc:scientificName`](https://dwc.tdwg.org/terms/#dwc:scientificName) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). |  |
| `Authority` | [`dwc:scientificNameAuthorship`](https://dwc.tdwg.org/terms/#dwc:scientificNameAuthorship) | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | |
| `Synonyms` |  | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | We could add them as separate taxa and linking them via `dwc:acceptedTaxonID`. Maybe later as nice to have. |
| `Sub-species level` | [`dwc:scientificName`] | [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). | `dwc:scientificName` =  `Species name` + `Sub-species level`. |
| `Native origin` | [`dwc:nativeRange`] | Description extension (`description.csv`). |
| `Recipient region:Country` | [`dwc:countryCode`](https://dwc.tdwg.org/terms/#dwc:countryCode) | [Species distribution](https://rs.gbif.org/extension/gbif/1.0/distribution_2022-02-02.xml) Darwin Core extension (`distribution.csv`). | Recommended best practice is to use an ISO 3166-1-alpha-2 country code. Example: `LT` for Lithuania. |
| `Recipient region:LME` | [`dwc:locality`](https://dwc.tdwg.org/terms/#dwc:locality) | [Species distribution](https://rs.gbif.org/vocabulary/gbif/distribution_status_2020-07-15.xml) Darwin Core extension (`distribution.csv`). | |
| `Recipient region:LME sub-region` | [`dwc:locality`](https://dwc.tdwg.org/terms/#dwc:locality) | [Species distribution](https://rs.gbif.org/extension/gbif/1.0/distribution_2022-02-02.xml) Darwin Core extension (`distribution.csv`). | |
| `Date of the first record` | `dwc:eventDate` | [Species distribution](https://rs.gbif.org/extension/gbif/1.0/distribution_2022-02-02.xml) Darwin Core extension (`distribution.csv`). | Examples: `1930`; `1939-1945`. |
| `Pathway` | [`dwc:pathway`](https://dwc.tdwg.org/terms/#dwc:pathway) | [Species distribution](https://rs.gbif.org/extension/gbif/1.0/distribution_2022-02-02.xml) Darwin Core extension (`distribution.csv`). | Follow the [Pathway Controlled Vocabulary List of Terms](https://dwc.tdwg.org/pw/). See [Patwhay](#pathway) section below for vocabulary mapping. |
| `Vector` | [`dwc:pathway`](https://dwc.tdwg.org/terms/#dwc:pathway) | [Species distribution](https://rs.gbif.org/extension/gbif/1.0/distribution_2022-02-02.xml) Darwin Core extension (`distribution.csv`). | `Pathway` - `Vector`  combinations will be mapped to [dwc:pathway](https://dwc.tdwg.org/terms/#dwc:pathway) vocabulary. [Patwhay](#pathway) section below for vocabulary mapping. |
| `Species status` | [`dwc:establishmentMeans`](https://dwc.tdwg.org/list/#dwc_establishmentMeans) | [Species distribution](https://rs.gbif.org/extension/gbif/1.0/distribution_2022-02-02.xml) Darwin Core extension (`distribution.csv`). |  Follow the [Establishment Means Controlled Vocabulary List of Terms](https://dwc.tdwg.org/em/). See [Species status](#species-status) section below for vocabulary mapping. |
| `Population status` | [`dwc:occurrenceStatus`](https://dwc.tdwg.org/terms/#dwc:occurrenceStatus) | [Species distribution](https://rs.gbif.org/extension/gbif/1.0/distribution_2022-02-02.xml) Darwin Core extension (`distribution.csv`). | Follow the [Distribution Status GBIF Vocabulary](Distribution Status GBIF Vocabulary)  See [Population status](#population-status) section below for vocabulary mapping. |
| `References` | `dwc:bibliographicCitation` and/or `dwc:identifier` | [Literature References](https://rs.gbif.org/extension/gbif/1.0/references.xml) Darwin Core extension (`references.csv`). | `dwc:identifier` contains DOI, ISBN, URI, etc referring to the reference. `dwc:bibliographicCitation` contains the text string referring to an un-parsed bibliographic citation. |

## Species status

The `Species status` field in AquaNIS will be mapped to the `dwc:establishmentMeans` field in Darwin Core following the [Establishment Means Controlled Vocabulary List of Terms](https://dwc.tdwg.org/em/). The mapping is as follows:

| AquaNIS species status |  `dwc:establishmentMeans` | Notes |
| --- | --- | --- |
| `Non-indigenous species` | `introduced` |  |
| `Cryptogenic` | `uncertain` |  |
| `Range expanding species` (planned) | `introduced` |  |

## Population status

The `Population status` field in AquaNIS will be mapped to the `dwc:occurrenceStatus` field in Darwin Core using the [Distribution Status GBIF Vocabulary](Distribution Status GBIF Vocabulary). The mapping is as follows:

| AquaNIS population status |  `dwc:occurrenceStatus` | Notes |
| --- | --- | --- |
| `Extinct/no recent record` | `absent` |  |
| `Rare/single record` | `rare` | Subclass of `present`. |
| `Common` | `common` | Subclass of `present`. |
| `Abundant` | `present` |  |
| `Very abundant` | `present` |  |
| `Outbreak` | `present` |  |

## Pathway

Mapping the `Pathway` and `Vector` fields to Darwin Core terms is not straightforward. The `Pathway` and `Vector` fields in AquaNIS will be lumped to `Pathway` field in Darwin Core and results in information loss. The mapping is as follows:

| AquaNIS Pathway | AquaNIS Vector |  `dwc:pathway` | Notes |
| --- | --- | --- | --- |
| Aquarium trade | Intentional organism release | `intentional` | |
| Aquarium trade | Transported water | `otherTransport` | Definition: "A catch-all term for any transport related dispersal that is not covered in other terms." |
| Aquarium trade | Waste discharge |  | |
| Culture activities | Aquaculture equipment | `fishingEquipment` | Definition: "Aquatic organisms moved between sites on equipment of recreational anglers and professional fishermen." |
| Culture activities | Associated water & packaging material | `aquacultureMariculture` | Alternative: `packingMaterial`, but it doesn't apply for "associated water". Definition of `packingMaterial`: "Organic material, particularly unprocessed plant material that is used to pack transported goods." |
| Culture activities | Intercontinental stock movement | `aquacultureMariculture` | |
| Culture activities | Regional stock movement | `aquacultureMariculture`  | |
| Culture activities | Unintentional release & escapees | `unintentional` | Definition: "The organism was unintentionally brought to a new region." |
| Leisure activities | Angling catch |  | |
| Leisure activities | Cultural releases | | |
| Leisure activities | Live bait | `liveFoodLiveBait` | |
| Leisure activities | Live souvenirs | `people` | Definition: "Organisms transported on people and/or their personal luggage."  |
| Leisure activities | Sport equipment | `fishingEquipment` | Definition: "Aquatic organisms moved between sites on equipment of recreational anglers and professional fishermen." |
| Leisure activities | Stocking for angling | `fisheryInTheWild` | Definition: "Fish stocked into the wild either to create a fishery or for recreational angling." |
| Leisure activities | Waste discharge | | |
| Live food trade | Intentional organism release | `foodContaminant` or `intentional` | `foodContaminant` stresses the source of introduction, while `intentional` stresses the act. Definition of `foodContaminant`: "Foods for human consumption, whether they are transported live or dead." |
| Live food trade | Transported water | `hitchhikersShip` | |
| Live food trade | Waste discharge | | |
| Management | Biological habitat management | | |
| Management | Construction equipment | `machineryEquipment` | Definition: "Organisms carried on the surfaces of or within heavy machinery and equipment." |
| Management | Construction materials | |  |
| Management | Release for biological control | `biologicalControl` | |
| Natural spread from neighbouring countries | Other natural vectors | `unaided` | Definition: "Organisms that spread by natural dispersal, without action or assistance by humans, from regions in which they are also alien." |
| Natural spread from neighbouring countries | Water currents | `unaided` | |
| Other canals | Canal de Midi (linking the Bay of Biscay with the Mediterranean Sea) | `waterwaysBasinsSeas` | Definition: "Organisms that dispersed through artificial waterways created to connect previosuly unconnected water bodies." |
| Other canals | Kiel Canal (linking the North Sea with the Baltic) | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Other canals | Northern waterway (linking the Baltic with the Ponto-Caspian region through Volga river canal system) | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Other canals | Rhone waterway (linking the North Sea with the Mediterranean) | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Other canals | Southern waterway (linking the North Sea with the Black Sea through Danube river canal system) | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Other canals | Central waterway (linking the Baltic Sea with the Black Sea through the Dnieper river canal system) | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Other canals | Other waterways | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Other canals | Irrigation canals | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Research and education | Gear movement | | |
| Research and education | Intentional releases | `intentional` | |
| Research and education | Unintentional release & escapees | `unintentional` | |
| Research and education | Waste discharge | | |
| Suez Canal |  | `waterwaysBasinsSeas` | Definition: see "Canal de Midi". |
| Vessels | Anchor and anchor chain | `hullFouling` | |
| Vessels | Ballast tank sediments | `ballastWater` | |
| Vessels | Ballast water | `ballastWater` | |
| Vessels | Ship’s hull | `hullFouling` | |
| Vessels | Sea chest | `hullFouling` | |
| Vessels | Others | `hitchhikersShip` | Safer alternative: `unintentional`. |
| Wild fisheries | Discard of by-catch | | |
| Wild fisheries | Fishing gear | `fishingEquipment` | |
| Wild fisheries | Live bait release | `liveFoodLiveBait` | |
| Wild fisheries | Live packaging material | `packingMaterial` | Definition: Organic material, particularly unprocessed plant material that is used to pack transported goods. |
| Wild fisheries | Processed live material | | |
| Wild fisheries | Stock movements | | |
| Wild fisheries | Transported water | `hitchhikersShip` | Definition: "Organisms that enter directly onto boats or ships and are transported by them to another location." |

## Metadata

Darwin Core metadata terms must be added to the [Darwin Core Taxon](https://rs.gbif.org/core/dwc_taxon_2024-02-19.xml) (`taxon.csv`). The metadata terms are:

| Dwc term | Value | Note
| --- | --- | --- |
| `language` | `en` |  |
| `license` |  | To be decided. Typically: `"http://creativecommons.org/publicdomain/zero/1.0/"` (CC0, the most open) or `"https://creativecommons.org/licenses/by/4.0/"` (CC-BY, the least open). |
| `rightsHolder` | `"Klaipeda University"` | To be decided. | 
| `accessRights` |  | To be filled in if present. Example at INBO: `"https://www.inbo.be/en/norms-data-use"`. |
| `datasetID` |  | This field can only be added after the very first publication of the dataset as it contains the DOI associated to the GBIF dataset. Example: `""https://doi.org/10.15468/3pmlxs""`. |
| `institutionCode` |  | To be filled in if present. Example at INBO: `"INBO"`. |
| `datasetName` | `"AquaNIS - Information system on aquatic non-indigenous and cryptogenic species"` | Just an attempt. To be decided by AquaNIS |

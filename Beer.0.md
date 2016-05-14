Beer Version 0
==============

- Beer 0 uses the QWERTZ keyboard layout to order the latin alphabet.
- q/Q = first letter; m/M = last letter.
- The letters `B`, `E`, `R` MUST be ignored and MUST NOT get replaced.
- All special characters except `.` and `,` MUST be ignored and MUST NOT get replaced.

#### Serialization
- `q-m` MUST be replaced by n-times `BEER` and the final character `∫`:

		q -> BEER∫
		w -> BEERBEER∫
		e -> BEERBEERBEER∫
		...

- `Q-M` except `B`, `E` and `R` MUST be replaced by n-times `µ` and the final character `∫`:

		Q -> µ∫
		W -> µµ∫
		R -> µµµµ∫
		...

- Special character:

		. -> BEER-BEER∫
		, -> BEER_BEER∫

#### Deserialization
- n-times `BEER` and the final character `∫` MUST be replaced by `q-m`:

		BEER∫      -> q
		BEERBEER∫  -> w
		...

- n-times `µ` and the final character `∫` MUST be replaced by `Q-M` except `B`, `E` and `R`:
 
		µ∫         -> Q
		µµ∫        -> W
		µµµµ∫      -> R
		...

- Special character:

		BEER-BEER∫ -> .
		BEER_BEER∫ -> ,

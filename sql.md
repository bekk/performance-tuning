# SQL-tuning tips 

## Oracle 

### Statistikk

For at optimizeren i Oracle skal kunne velge den beste strategien for å utføre en spørring, må den ha fersk statistikk på indekser og tabeller. Per default genererer Oracle ny statistikk en gang hver dag, typisk om natten. Dersom innholdet i en tabell er veldig flyktig (> 20% endrer seg etter statistikk generering), vil ikke statistikken være særlig korrekt mer, og statistikken bør oppdateres. 

Tipps! Dersom man batch loader store mengder data, bør også statistikken regenereres.

### Indekser

Indekser kan dramatisk øke ytelsen på en database spørring. Generelt kan man si at indekser brukes i forbindelse med følgende typer spørringer:

1. likhet (f.eks. _where id = 5_)
2. ubegrenset utvalg (f.eks. _where id < 10_, eller _where id <> 20_)
3. begrenset utvalg (f.eks. _where id between 10 and 20_)

#### Selektivitet

Selektivitet er den estimerte andelen av et resultatsett verdi som tilfredsstiller et eller flere predikater (enklere sagt: fordelingen av verdier i en kolonne), og er avgjørende for om en indeks benyttes i forbindelse med en spørring.

Generelt kan man si at jo lavere selecktivitet, desto større er effekten av å benytte en indeks. 
Optimizeren bruker selektivitet (basert på statistikk) for å avgjøre om den skal benytte seg av en indeks i en gitt spørring, så om du har gjort store endringer som påvirker selektivitet, kan det være aktuelt å regenerere statistikk. 

#### Datatype mismatch

I forbindelse med spørringer mot indekserte kolonner, er det vikitg at datatypen i spørringen er lik med datatypen på indeksen. Selv om du får kjørt spørringen med implisitt datatype-konvertering (f.eks. fra int til string), vil ikke indeksen bli brukt.

#### NULL values

I eldre versjoner av Oracle (før 11g) var det ikke mulig å indeksere NULL-verdier. Det gjorde at det ville bli kjørt en full-table-scan.

For å komme rundt dette, kan man lage en funksjons-basert indeks som bruker den innebygde NULL-verdi SQL-funksjonen for indeksere felter med NULL-verdi.

Se flere detaljer her: http://www.dba-oracle.com/oracle_tips_null_idx.htm

#### Function-based indexes

En funksjonsbasert indeks beregner verdien av et uttrykk som involverer én eller flere kolonner og legger dem i indeksen.
...

#### Composite index


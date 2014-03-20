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

#### Datatype mismatch

#### Null values

#### Function-based indexes

#### Composite index


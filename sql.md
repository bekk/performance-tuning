# Topp 10 SQL-tuning tipps 

## Oracle 

1. Statistikk
   For at optimizeren i Oracle skal kunne velge den beste strategien for å utføre en spørring, må den ha fersk statistikk på indekser og tabeller. Per default genererer Oracle ny statistikk en gang hver dag, typisk om natten. Dersom innholdet i en tabell er veldig flyktig (> 20% endrer seg etter statistikk generering), vil ikke statistikken være særlig korrekt mer, og statistikken bør oppdateres.
2. 
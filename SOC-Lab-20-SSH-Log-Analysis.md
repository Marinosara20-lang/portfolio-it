SOC Analyst Lab 20 — Analisi dei log SSH

Area: Cybersecurity / Security Operations Center (SOC)
Livello: Principiante
Ambiente: iSH su iPhone — Alpine Linux
Tipo di esercitazione: Simulazione didattica

1. Obiettivo

Analizzare log di autenticazione SSH per individuare possibili accessi non autorizzati e ricostruire le attività successive all’accesso.

2. Strumenti utilizzati

* Linux shell
* Comando grep per filtrare i log
* Comando grep -c per contare le righe corrispondenti
* Analisi della sequenza temporale degli eventi

3. Eventi rilevati

Durante l’analisi dei log simulati sono stati individuati:

* Quattro tentativi di autenticazione falliti per l’utente luca.
* Un successivo accesso riuscito dallo stesso indirizzo IP.
* Due attività eseguite tramite sudo: il comando id e il comando passwd.
* Una dichiarazione dell’utente secondo cui non avrebbe effettuato l’accesso.

4. Analisi e valutazione del rischio

La sequenza di tentativi falliti seguita da un accesso riuscito, unita alla negazione dell’utente, costituisce un insieme di indicatori sospetti.

Tuttavia, i dati disponibili non permettono di confermare definitivamente un attacco informatico né di identificare il responsabile.

Il comando passwd, inoltre, non dimostra da solo che sia stata modificata una password.

5. Azioni investigative successive

In un ambiente reale, sarebbe opportuno:

1. Verificare l’identità dell’utente e la legittimità dell’accesso.
2. Correlare gli eventi con altri log disponibili.
3. Approfondire le attività eseguite dopo l’autenticazione.
4. Verificare eventuali modifiche agli account e alle configurazioni.
5. Seguire le procedure aziendali di risposta agli incidenti, preservando le prove.

6. Conclusione

L’esercitazione ha permesso di applicare tecniche di analisi dei log Linux, individuare comportamenti potenzialmente anomali e formulare una prima valutazione del rischio.

Risultato: individuazione di un possibile accesso non autorizzato da approfondire.

Nota: tutti gli eventi utilizzati in questo laboratorio sono simulati a scopo formativo e non provengono da un sistema reale.

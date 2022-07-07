# Notes 

- wie r vorgeben? -> kommt vom Betreiber -> also Vorschrift aus Skript nicht sehr relevant 
- Lineare MPR -> quadratische Kostenfunktion J(x,u) -> lineares System, "least square", Nebenbedigungen müssen linear sein
    - führt auf quadratisches Programm 
      
- nur Gleichheitsnebenbedingungen -> unbeschränkte lineare MPR -> Reglereinstellung ist konstant und kann berechnet werden

- Stabilität nicht Kern der Vorlesung zu MPR, wird kein Scherpunkt in der Prüfung

- Hohe Anwendung durch:
- MPR ist das einzige Verfahren, dass sicher Beschränkungen einhalten kann
- Optimalität

- Wahl von N1 und N2 ist sehr prüfungsrelevant 
- -> N1 = d, N2 erfasst wesentliches Systemverhalten (kann z.B. an Einheits-Sprungantwort ermittelt werden)
- N1>d ist nicht sinnvoll, da das System schon auf Änderungen reagiert, die Abweichung vom Sollwert aber nicht in Kostenfunktion enthalten sind
- (siehe Skizze)

- N1<d oder Nu>N2-d erhöhen Aufwand ohne weiteren Ertrag
- Nu klein führt zu aggressivem Verhalten. aber auch zu schlechtem Systemverhalten, da der Regler versucht, in wenigen Zeitschritten Ziel zu erreichen
- z.B. bei Unterschwingen nicht sinnvoll

- Viel Zeit: Nu = N2-d ist maximales Nu das möglich ist, Nu>=3 meist ausreichend, aber nicht unbedingt optimal
- die letzten d Stepps werden nicht gelernt (vgl. mit ILR)

- heufiges Mittel zur Verbesserung der Berechnungszeit: Stellgrößeneingriffe werden nicht äquidistant verteilt (nicht Teil dieser Veranstaltung)

- Wahl von Nu ist unabhängig von der Wahl von N1

- Indexdefinition für k=0 und k=1 nachschauen -> hat Einfluss auf Vorschrift zur Berechnung von Nu, N2...

- N2 ist Maß für Prädiktionsfähigkeit der Regelung

- MPR ist super dafür geeignet MIMOs mit schlechtem RGA zu regeln


- klassischer industrieller Anwendungsfall: eine zentrale MPR, die in der Leitstelle über einen längeren Zeitraum einen guten zukünfigten Sollwertverlauf
- ausrechnet. Die berechneten Sollwerte werden im Rhamen einer Kaskadenstruktur an niedere Regler (mit geringer Leistung des microC) weitergegeben


# Solved

- sind die Ausführungen zu nichtlinearen MPR im Skript als Ausblick zu verstehen oder sind die vorgestellten Verfahren prüfungsrelevant
- Dynamic Matrix Control (DMC), Generalized Predictive Control (GPC), Interpoint-Methode, BGFS-Formel, DFP-Formel für nichtlineare MPR
- Vorlesungsfolien sind prüfungsrelevant, in Skript werden nur weitere Tipps gegeben. Kann hilfreich sein, ist nur ein Vorteil für
- eigene Antworten in Prügungsfragen


- Warum braucht eine ILR einen Zeitschritt zur Berechnung des neuen Stellgrößenverlaufs, aber die MPC kann die Stellgrößenänderung von 
  Schritt k innerhalb des Zeitschritts k berechnen und ausgeben?
    - nicht vergleichbar. ILR versucht gar nicht, innerhalb des Zeitschritts auf auftretende Änderungen zu reagieren.

- Führt eine lineare MPC ohne Beschränkung zu den gleichen Parametern des Zusandsreglers, wie ein LQR, falls die selben Forderungen an Q und R gestellt werden?
    - nein: MPC ist zeitdiskret, endlicher Zeithorizont, MPR rechnet in jedem Zeitschritt nochmal nach. 

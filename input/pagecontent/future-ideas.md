# Workflow
- ggfs. Extraction direkt in Bundle, um damit dann Referenzen direkt statisch vorzugeben -> weil diese beim POSTen erhalten bleiben
- source of truth -> was wenn widersprüchliche Werte aus unterschiedlichen Quellen / Zeitpunkten auftauchen (z.B. Pflegegrad war vor 2 Jahren noch 3, jetzt 4, was stimmt? Wie werden Konflikte aufgelöst? 2 unabhängige Observations?)
- logische Validierung eines QuestionnaireRessponse vor Extraction(einfacher), um inhaltliche Fehler beim Ausfüllen zu verhindern (Invariante? CQL?) alles, was man nicht über Bindings, RegEx oder enableWhan, maxPlaces einschränken kann
- 

* Abläufe für Synoptic Cancer Reporting einmal darstellen
* langfristig ggfs.  als Ergänzung zum SNOMED synoptic Cancer Reporting IG (Link!)
* Ergbnisse dort vorstellen und mit einarbeiten 
* Daher: am besten direkt auf Englisch verfassen (lieber kurz und knapp auf Englisch als ausführlich auf deutsch)  
* "Testing" auf dem Community Treffen 
* Wie bekommt man die semantische Annotation in ein Pathosystem?  
* z.B. über semantisch vorannotierten Fragebogen, der vom Pathologen ausgefüllt wird
* Woher weiß der Pathologe, welchen Fragebogen er ausfüllen soll?  
* Entitätbezogene Formulare,   
* teils durch initiale Fragestellung des klinikers ferstgelegt,   
* teils durch Pathologen / Studendiagnostik festgelegt  
* Wie können solche Formulare bereitgestellt werden?  
* FHIR Questionnaires  
* RedCAP für Research, aber für Versogung lizenztechnisch schwierig / teuer

* Wie kann man FHIR aus PathoLaborsystemen rausbekommen? 
	* IHE Structured Patho Report
	* FHIR Diagnostoc Report
	* Kombination in MII Patho report
		* Struktur vorgibt, die sowohl Daten strukturiert
		*  als auch Dokumente rendern kann
* Wie kriegt man jetzt die Annotierten Beobachtungen in FHIR? 
	* Als z.B. Patho Finding unter DiagnosticReport.result 
* Das kann ich im Prinzip irgendwie machen, wie mache ich das denn in FHIR? 
	* Extraction 
		* Observation
		* Definition
		* StructureMap
		* Template
	* Dafür müssen aber auch die Questionnaires schon die richtigen Extension
	* Daher muss es eine Instanz geben, die sowohl die Questionnaires als auch die Zielspezifikation definieren kann
 
Grafik übergang von Kliniker zu Labor
-> Service Request mit Indikation/ Fragestellung
altenrativ nach SDC über Task 
(nach POST muss man die ID / Etag merken, damit man updaten kann)
(PATCH Befehl? )
Laborsystem schickt dann Questionnaire für die klinischen Vorinformationen
Kliniker füllt aus, Service request wird geupdated und verschickt
Probe wird verschickt (OrderEntry)
Prepopulation
Proben werden im Labor kontrolliert, systematisch erfasst, registriert und pseudonymisiert 
Untersuchung wird durchgeführt, parallel dazu / danach Erfassung mit synoptischem Fragebogen
-> Auswahl des Fragebogens und der notwendigen / optionalen Module durch Pathologen,
 
(gesetzt den Fall, dass es verfügbare ICCR-Fragebögen gibt)
 
Beenden des Fragebogens, Erstellen des Befundes
Erstellen eines DiagnosticReports als Datenelement 
Erstellen eines Bundels als signiertes Dokument für Archiv und Legal Reasons
Erstellen einer Composition für das Rendern als menschenlesbares Dokument
 
SMART Security on FHIR ! 
auf EHRs 
SMART on FHIR am Anfang (Patientendaten, Krankheitsdaten / Laborwerte
SMART on FHIR am Ende (DiagnosticReport in EHR hinterlegen)
ePA?
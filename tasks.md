# TODOs @Home
- [x] Nvim: RunConfigs Arbeit ans laufen bekommen
- [x] Nvim: Optimize debugging in neovim
- [ ] AI-Engineering: Mental Model -> Wie entwickle ich? (Provider, Services, Security, Entities, Dao)
- [ ] AI-Engineering: Teacher / Learning (https://www.skills.sh/)
- [ ] AI-Engineering: Agentic Security
- [ ] AI-Engineering: Subagent Optimizing + Automatic Agent-Swarms
- [ ] TEST: Docker Sandbox for Local Development (sbx)
- [ ] TEST: Create a MCP Server (with Java) and run an agent (Claude Code Subscription) on it
- [ ] Neovim: Java - Analyzing / - Profiling Ingegration via JFR 
    - Einlesen und Ausprobieren von JFR
    - Möglichkeiten mit Cursor in Config einbauen
- [ ] Feierabend AI - Trigger: DENK nach was noch automatisiert werden kann
    - [x] Ticket Briefing 
    - [ ] MR Briefing
    - [X] Generating Tests based on exmaples and for services (Unit) and dao (IT) als command
    - [ ] Jira Integration on AI to Review new Tickets, Analyse and Rate them, Approve or Abort them/Send them back with hints
- [ ] Decision Engineering - Research
- [ ] Spec-Driven-Development (SDD)
- [ ] Apple Containers
- [ ] Shors Algorithm -> Quantum Algorithm
    - ML-KEM is available in Java 24+ -> try it out

# Valhalla
- [!] Demo Projekt anlegen und testen
- [?] Warum sollten Records nicht per default value sein?
- [?] Wenn GC in einem anderen Thread laufen, wieso haben wir dann Stop The World?
- Leben Value Objects auf dem Stack? -> JA DIGGA JAAAAAAAAAAA
- Wenn ich value in einem anderen datentyp wrappe, der auf dem heap lebt (zb array) -> flattening, sondern  scarlarization (stack)
- Vorteil Flattening: Gesamter Speicher liegt an einem Platz, sonst Referenzen, die alle woanders liegen ( no pointer chasing and dereferencing )
- [?] FLattening: wenn ich hier richtige values habe und keine pointer, werden die values dann noch vom GC bearbeitet oder nicht gespeichert?

# Hacker (Security)
- [ ] nvim Plugin: Detection of security issues in code + CVEs of Dependencies
- SQL Befehl in SQL Injection um Zugriff auf Postgres zu bekommen auf Hacker-Server -> Welcher? 
- Swagger-UI Endpoint darf nicht exposed sein
- Shodan.io
- Rate-Limiting -> Man kann nicht Brute-forcen, weil man nicht unendlich mal draufzugreifen kann
- JWT: keine wichtige Informationen in den claims speichern
- [ ] GitLeaks + Trufflehug: Pre-Commit Hook was checkt, ob man PW/Auth-Infos usw. im Code leakt + Integrierbar in der Pipeline
    - Oder: sonarqube
- Checkov: IAAC 
- [ ] Depscan -> Analyzing SBOM for CVEs (Dependency Analysis) -> reicht, wenn man einfach nur eine Datei gibt
    - Syft: SBOM Analyzing enriched on container level, OS level etc. + your application
    - DependencyTrack: Monitoring
    - sontatybe lifecycle -> Integration in the pipeline and make it fail with a rule when having CVE xyz
- [ ] Threat Modelling: STRIPE Framework 
- [ ] Thread Atlas
- [ ] Security Monitoring: splunk, elastic, azure log analytics, amazon cloudwatch (SIEM Tools)
- [ ] CNAPP: Showing the attack path in cloud based on exposures (open CVEs) -> Sentinal, PaloAlto, Wiz
- [ ] ASPM (Application Secure Posture Managment): Scandog.io
- [ ] TryHackMe
- Maven: Group.id muss die domain sein, die von dir reserviert ist -> hacker können keine packages unter dieser domain fake hochladen und malware installieren
- tips
    - critial
        - clear versions, not latest
        - mvn clean isntall --check-checksum
        - git .lock - files (like package.lock) -> shows checksum for integrity
        - mvn check depencies Command
        - maven "remote repository filter" -> makes pipeline faster as well 
        - Renovate/Dependabot
        - use hardened images -> Versionen, aber jemand hat sich die Arbeit gemacht alle vulnerabilities für die Version zu fixen
        - Jarsigner -> signs your jar with a certificate to make sure its not modified by someone and its yours

# Security: Toxic MCP
- Snyk Agent Scan -> Free tool to scan Skills or MCPs for harness content and instructions

# ORM OMG: JPA Pitfalls
- open-in-view Property: Keeps DB Connection after actual transaction when being in the view (eg Thymeleaf) -> set it off since we dont do DB Interaction there
- spring.database.connection.mode=lazy (Spring boot v. 4.x) -> postpone readonly=true when using the db and not at the start of the methode
- spring.datasource.hikari.auto-commit=false -> hibernate does not need to do it every method and open DB only for this flag
- transcationalTemplate.execute -> when DB Connection is hold -> transaction -> non-transcational logic -> transactional.. we hold the db connection for too long in the non-transcational part and do custom transactionals (or exclude it in a another @Transactional)
- Intellij Plugin: Hibernate Plugin for Debugging
- [ ] Gatling.io: load testing for java / Hibernate

# SVN

## Fragen
- nach dem Sitzungsgelder aus Sitzungen erzeugen hätte ich Fragen erlaubt -> why not?

# Architekturen und Entwurf von Rechnersystemen

*Course taught at the Technical University of Darmstadt.*

## Übersicht

*   Credits: 5 CP
*   Dozent: Andreas Koch
*   Betreuer: Jaco Hofmann
*   Vorlesung: Mittwochs 13:30–15:10 in S1|01 A01 und Donnerstags 16:15–17:55 in S105|122.
*   Prüfungsart: Klausur, vorraussichtlich am 25.2.2019.
*   Links: [Moodle](https://moodle.informatik.tu-darmstadt.de/course/view.php?id=476), [Veranstaltungswebseite](https://www.esa.informatik.tu-darmstadt.de/twiki/bin/view/Lectures/AERWS18De.html).
*   Notizen zur Vorlesung: [PDF](notizen.pdf) (*work-in-progress*).

Diese Veranstaltung wird aufgezeichnet. Die Übungsaufgaben sind freiwillig. 

## Nützliches

*   [Bluespec Reference Card](material/BSV_ref_card.pdf)
*   [Bluespec by Example](material/bsv_by_example.pdf)
*   [Bluespec Reference Guide](material/reference-guide.pdf)
*   [Bluespec User Guide](material/user-guide.pdf)
*   [RBG Zugang](tutorials/rbg.md)
*   [Vim einrichten für Bluespec](tutorials/vim.md)

## Inhalt

*   Technologische Grundlagen und Trends der Mikroelektronik
*   Entwurfsflüsse für mikroelektronische Systeme
*   Beschreibung von Hardware-Systemen
*   Charakteristika von Rechnersystemen
*   Architekturen für parallele Ausführung
*   Speichersysteme
*   Heterogene Systems-on-Chip
*   On-Chip und Off-Chip Kommunikationsstrukturen
*   Aufbau eingebetteter Systeme, z.B. im Umfeld von Cyber-Physical Systems

## Vorlesungen

*   2018-10-17. [Aufzeichnung](http://www.esa.cs.tu-darmstadt.de/campus/AER-20181017.avi)
*   2018-10-18. [Aufzeichnung](http://www.esa.cs.tu-darmstadt.de/campus/AER-20181018.avi)
*   2018-10-24. [Aufzeichnung](http://www.esa.cs.tu-darmstadt.de/campus/AER-20181024.mp4)
*   2018-10-25. [Aufzeichnung](http://www.esa.cs.tu-darmstadt.de/campus/AER-20181025.mp4)
*   2018-10-31. [Aufzeichnung](http://www.esa.cs.tu-darmstadt.de/campus/AER-20181031.mp4)
*   2018-11-01. [Aufzeichnung](http://www.esa.cs.tu-darmstadt.de/campus/AER-20181101.mp4)


## Folien

*   [Intro Basic](folien/intro_basics-handout.pdf)
    *   Organisatorisches
    *   Einführung der Mikroeletronik
    *   Hardware-Entwurfstechniken
    *   Fundamentale Entwurfsmethoden
    *   Verfeinerter Ablauf der Synthese
    *   Verifikation
    *   Synthesebeispiel
    *   Rekonfigurierbare System-on-Chips
*   [Bluespec](folien/bsv.pdf)
    *   Einführung
    *   BSV Werkzeugfluß
    *   Syntaxbeispiele
    *   Bedienung
    *   Grundlegende Syntaxelemente
    *   Ausführungssemantik
    *   Parallelität und Nebenläufigkeit
    *   Datentyp `Maybe`
    *   Mehr Nebenläufigkeit
    *   Von BSV zu Verilog
*   [Xilinx Zync System-on-Chip](folien/zynq-soc2.pdf)
    *   XILINX ZYNQ 7000 RSOC
    *   ARM Cortex-A9 Prozessorkern
    *   APU On-Chip Memory (OCM)
    *   Programmierbare Logik (FPGA)
    *   Hard Core vs. Soft Cores
    *   SCHNITTSTELLEN ZWISCHEN PROZESSOR UND FPGA
    *   HP vs ACP
    *   ARM AMBA AXI4
    *   IP BLÖCKE UND HIGH-LEVEL SYNTHESE
*   [TAPASCO](folien/tapasco-handout.pdf)

## Übungsblätter

*   [Übungsblatt 1](uebungen/ueb01_no_lsg.pdf): Einführung in grundlegende Bluespec-Sprachkonzepte.
*   [Übungsblatt 2](uebungen/ueb02_no_lsg.pdf): Finite-State-Machines in Bluespec.
*   [Übungsblatt 3](uebungen/ueb03_no_lsg.pdf): Verwendung von BlueCheck zum testen von Bluespec-Modulen. 
*   [Übungsblatt 4](uebungen/ueb04_no_lsg.pdf): Vorteil von Berechnungen auf Hardwarebeschleunigern.
*   [Übungsblatt 5](uebungen/ueb05_no_lsg.pdf): Weiterführung von Übungsblatt 4
*   [Übungsblatt 6](uebungen/ueb06_no_lsg.pdf): Weiterführung von Übungsblatt 5
*   [Übungsblatt 7](uebungen/ueb07_no_lsg.pdf): Weiterführung von Übungsblatt 6

## Materialien

*   D. M. Harris und S. L. Harris: *Digital Design and Computer Architecture, 2. Ed*, MKP, 2012.
*   Bluespec Online-Dokumentation der RBG unter `/usr/local/bluespec/doc/BSV`.
*   Einführungsbuch *Bluespec by Example*.
*   L. Crockett, R. Elliot, Martin Enderwitz, Bob Stewart und D. Northcote: *The Zync Book*, Strathclyde Academic Media, 2014. Frei verfügbar auf <http://www.zyncbook.com/>.

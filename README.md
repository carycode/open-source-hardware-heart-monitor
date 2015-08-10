
The open-source hardware heart monitor project
----------------------------------------------

* 2014-03-25:DAV: first public posting.

* safe
* make visible some of the normally-hidden workings of the human heart
* open source hardware

The various electronic subsystems can be arranged to build:

* Open source Holter monitor:
able to scale down to a standard 4 electrode Holter monitor.
Comfortable -- lightweight even including the batteries.
Long run-time.
etc.
* Open source body surface potential mapping:
able to scale up to record from dozens of electrodes simultaneously.
(The so-called "12-lead EKG" has 10 electrodes.)

Body surface potential mapping
is the original motivation for the openheart project.

DAV and Dr.K wanted some body surface potential mapping data
in order to test out some theories
and heuristics and ideas we had
for approximate solutions to
the inverse electrocardiography problem.
Off-the-shelf devices for recording body surface potential data were
beyond DAV's budget at the time,
but DAV's experience with
mixed microcontrollers and data acquisition
made him think it that one could be built for a more reasonable price.

The inverse electrocardiography problem
is the problem of making a 3D picture of the electrical activity of the heart,
when all we have is the body surface potential data.

DAV is buying the first prototype PCBs from OSHPark
(Open Source Holter (OSH), OSHPark -- see the connection?)

We thought about using 
the acronym IEKG -- Improved Electrocardiogram --
but
the "Institut für Ethik und Kommunikation im Gesundheitswesen"
(the institute for ethics and communication in health care)
already used the acronym IEKG.

Still looking for a catchy acronym.

* the open-hardware Holter heart monitor (OHHHM).

Other open-source EKG systems:


*
Biometric daughter board for Hoarder board
The daughter board allows the hoarder board to collect EKG, EMG, EEG, skin conductance, and temperature signals.
http://vadim.oversigma.com/Hoarder/Biometrics.htm
Hoarder aka Swiss Army Knife (SAK) board,
http://vadim.oversigma.com/Hoarder/Hoarder.htm
http://capsil.org/capsilwiki/index.php/Hoarder_Board
(_)
designed as a part of the Every Sign of Life project.
http://vadim.oversigma.com/esl/esl.html

The Hoarder Biometric daughter board
uses a INA2321EA instrumentation amp
and some OPA4336EA op amps
to amplify a EKG EMG EEG signal.

*
SHIELD-EKG-EMG
open source hardware
which allows the Arduino and shield-compatible Arduino-like processor boards
to capture electrocardiography and electromyography signals.
https://www.olimex.com/Products/Duino/Shields/SHIELD-EKG-EMG/open-source-hardware

Schematic and board layout released under
Creative Commons Attribution-Share Alike license.

input protection circuit

instrumentation amplifier:
INA321EA
TLC277IDR for DC removal

followed by
MCP607 op-amp with gain control pot

No ADC on the board --
feeds the analog signal into the Arduino A0 analog input.
(The Ain-sel header can be hardwired to
feed the analog signal to any Arduino analog input).

*
instrumentation amplifiers:
http://www.mouser.com/Semiconductors/Integrated-Circuits-ICs/Amplifier-ICs/Instrumentation-Amplifiers/_/N-6j73w/
(_)

*
OpenEEG-related software
http://openeeg.sourceforge.net/doc/sw/


Ajay Bharadwaj.
"Accurate ECG Signal Processing".
http://www.cypress.com/?docID=28762
http://www.eetimes.com/document.asp?doc_id=1278571 (_)
mentions that tyical ECG signals at the electrode
include
* typically DC +-300 mV half cell potential offset with Ag/AgCl electrodes
* typically ~1.5 V common mode 50 or 60 Hz noise picked up from power lines
* typically +-0.5mV actual desired signal (p. 2)
* typically +-2 mV desired signal 0.05 to 150 Hz. (p. 3)
The standard EKG paper (with 1mm small square boxes, 5mm large square boxes)
runs at
25 mm/s
10 mm/mV


"ECG and EEG Applications: Quick Reference Guide"
http://www.ti.com/lit/sg/slyt416/slyt416.pdf
via
http://www.ti.com/solution/ecg_electrocardiogram (_)
mentions
ADS1291
ADS1292 2-channel Holter
ADS1298 12-lead ECG systems
OPA334 zero-drift, low-offset, single-supply op amp
OPA335 zero-drift, low-offset, single-supply op amp
INA333 low-power instrumentation amplifier: 50 nV/sqrt(Hz)
www.ti.com/sc/device/INA333


http://www.ti.com/solution/ecg_electrocardiogram (_)
mentions
<q>
When a low resolution (16 bit) ADC is used, the signal needs to be gained up significantly (typically 100x - 200x) to achieve the necessary resolution. When a high resolution (24bit) sigma delta ADC is used, the signal needs a modest gain of 4 - 5x. Hence the second gain stage and the circuitry needed to eliminate the DC offset can be removed.
</q>


"Stephen Lee and John Kruse"
"Biopotential Electrode Sensors in ECG/EEG/EMG Systems"
http://www.analog.com/static/imported-files/tech_docs/ECG-EEG-EMG_FINAL.pdf
mentions
Ag/AgCl has a relatively low half-cell potential of abou 220 mV.
With properly prepared skin, body to electrode impedance
is typically about 5 kOhm ...  500 kOhm is encountered frequently ...
The cardiac signal (differential voltage across a person's chest)
is typically 1.8 mV riding on a DC offset of up to 300 mV.
???  "The input bias current of the front-end amplifiers
can polarize the electrode" ???


http://www.analog.com/static/imported-files/overviews/Home-Is-Where-The-Heart-Is.pdf
mentions
Analog Devices ADAS1000-3: 3-lead ECG analog front end (AFE)
Analog Devices ADuCM360 fully integrated, 24-bit data acquisition system 





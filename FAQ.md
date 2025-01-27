# <span style="color:green">Q&A</span>

Q: &ensp;How long does it take to build and test a DCDC?<br>
A: &ensp; If you are really nuts, you can do it as a single person in one day (but I don't recommend this). There are currently 190 components on the board, which can be soldered in 2 - 3 hours with good preparation and experience using solder paste (without stecil) and hot air. The longest time is needed to find and assign the correct components to the footprints. A board preassembled by JLC PCB (SMD only) may already contain approx. 80% of the components. This means that only about an hour is needed for the remaining components. The coil formers for the transformer require 2-4 hours depending on the SLA printer. Winding takes approx. 1 hour. Grinding and gluing the ETD cores takes approx. 30 minutes. Cleaning and drying of circuit boards, cores, SLA prints: total approx. 1 hour.<br>
If you want to build it properly, plan 1-2 days for building it, and 1-2 Weeks for lab testing before installing it.

Q: &ensp; Can I buy a whole converter from you?<br>
A: &ensp; Currently no. Assembling and testing it in a proper way would be so much work that (depending on demand) I couldn't do anything else. The cost of the effort would be many times higher than the material value of the converter, and the DIY idea is somewhat lost. The legal responsibility in the event of problems or errors is also difficult. All tests of a converter up to completion are carried out to the best of my knowledge, but are not recognised or certified. However, it might be possible to obtain partially assembled boards and UL94 V-0 coil formers for further assembly from me.<br>
_Are you interested in making a larger production of the converter? Feel free to contact me via Reddit!_<br>

Q:	&ensp;HELP! QUICK!!!!1! DCDC broke!<br>
A:	&ensp;Well, that's you turn to learn ;)<br>
Please open a new issue. I will deliberately be slow in answering urgent questions, as there was enough time available with good planning - so at least try not to make it look urgent.
Provide as much information as possible (e.g. how long the converter has been turned on, ambient temperatures, input voltage, output load, ...) and add pictures if relevant.
I will try to help to the best of my availability, but as this is not my job, I cannot guarantee anything.

Q: 	&ensp;I need [insert voltage here], can I do that?<br>
A: 	&ensp;You could change the feedback voltage divider for small adjustments (+-2V or so from 24V).<br>
But if you need 12 V .. 48 V you should alter the number of secondary windings, otherwise you will get in trouble with the resonant design.<br>
Note, that the output capacitors and SR-FETs must be altered accordingly!
	
Q: 	&ensp;I need more Power!<br>
A: 	&ensp;Currently the design is limited by thermals. Adding a strong Fan would allow to draw 750 W continously.<br> 
More than 750 W would exhaust the resonant cicuit, requiring different C_res and L_m/L_r.<br> 
I was able to pull 1500 W from an older Version with a lent source/sink which was able to handle that much. <br> 
But currently I do not own such a powerful source/sink to conduct test in this area.<br>

Q: 	&ensp;Where do I get a cheap high voltage source for low power testing?<br>
A: 	&ensp;I have been using one for 10€ from amazon for many years, which can generate up to 
800 V (when both -+400 V rails are used) from a 8 to 32 V source (15 V input delivers most HV power, 25 W max.).
If you want to support me, you can use my affiliate link where I get a small commission 
when a purchase is made: https://amzn.to/3TRJJif<br>
In the docs there is an additional folder 'HV Source' for a 3D-printed case which also 
uses a rotary potentiometer instead of the trim pot. If there is enough interest, I will make a build guide for it.
Please add at least 100 uF (check voltage rating!) externally to the output, otherwise the feedback loop can be unstable in certain situations.<br> 

Q: &ensp; How reliable is the converter?<br>
A: &ensp; As the converter is being developed on an ongoing basis, it is normal that a few problems may occur at the beginning. Thanks to the practical experience of the last 3 years and iteraton over 6 PCB versions, these problems continue to diminish. To make sure that the converter does not cause any surprises in the field test, there are some tests that I carry out in advance.
Typical tests are:
- UVP/OVP limit tests (test if the voltage protection works properly)
- no load tests (confirm the max. switching frequency)
- full load test for the intended voltage range (check temperatures with themal imaging)
- efficiency test for the intended voltage and load range
- mad scruti test: Try destroying the converter by playing around with the DC/DC enable switch (precharge and turn on/off sequence should be always in safe state)
- hot box test: put the converter inside a small enclosure (2-5l volume) for ≥ 30 mins and record the temperatures inside. A restart should be possible after 30 mins and ≥ 60°C air temperature
- turn-on tests: Monitor switching frequency, inrush currents and voltages (Input/Output/C_r) to confirm that no component limits are exceeded
- Control loop stability test: Apply load jumps and short circuits (!) to the output and observe whether the control loop overshoots and reacts quickly enough
- Miscellaneous: Start capacitor max. start time and long-term storage test (leakage current), Internal power supplies (voltages/currents), Synchronous rectification Waveforms 
- Transformer Isolation Test (> 2kV AC 50 Hz) 
In total there are currently 197 documented tests.
This may sound like a lot, but as this converter is still a work in progress, this effort must be made for every new version and every new build. Once these tests have been passed, some tests no longer need to be carried out (or less strict) for further builds of the same version.
These tests ensure that the converter is very reliable under real conditions. The first converter to pass all the tests (version 8) has been running faultlessly in a racing car for 2 years (and counting). Version 9-2 was installed without a hot-box test based on previous experience ... well, I should have done it once. It turned out later that the converter could no longer reliably start from 55°C upwards due to a OTP measurement problem. A quick-fix solved the problem on the v9-2, a proper solution is installed on the v9-3.<br>

Q: 	&ensp;Why is some text not editable?<br>
A:	&ensp;I like to use a font (Futured) for visuals which is not pre-installed on most systems. 
Importing it as a logo is easier to retain it.<br> 

Q: &ensp;Why are there almost no reference designators on the pcb?<br>
A: &ensp;They do exist! But most of them are hidden below the components. Having them placed around the components looks messy, especially if there is no space left.<br>
For manual assembly, I use the HTML BOM to look up the positions anyway, so I don't really need the designators. At best, I use them for a second look.<br>

Q: 	&ensp;Some 3D models on the PCB are missing.<br>
A:	&ensp;They are not included due to licence terms. However, you can download them from https://www.samacsys.com/ using the Mouser link provided in the properties of the KiCAD components. For quick access: highlight part, press "D".<br>

Q: &ensp;Can a Würth LLC transformer be used instead of a self-wound transformer?<br>
A: &ensp;Physically the footprint does not fit with the current design, but as of v9-3 there would be enough space. Technically you could use them, but their max. power is 200 W and the frequency range is quite different. If one really wants to utilize them, it would be doable. But for now, their limited power is the main reason not to use them.<br>
I'm aware, that building and testing the transformer is might the most complicated part of this whole converter, since it requires tools that not everyone has.
But also think of what learnings and possibilities come from this, so it might be worth the tools, especially if you want to build one every season.

Q: &ensp; KiCAD is throwing lots of errors/warnings on DRC?!  <br>
A: &ensp; This is an expected and desired behaviour. Due to the high voltages on the PCB, I had to ensure that the required clearances were not violated.
Therefore, I created custom rules (.dru file) that assign clearances to critical nets. However, these clearances do not take into account the potential differences. 
So a 600 V net would be 1.2 mm on the outer layers, but the clearance to the high voltage source (612 V) would still be 1.2 mm, even though there is only a 12 V difference.
To solve this correctly, I would have to come up with a rule for the distance between each net. Mathematically, this would be the sum (k) for k = 1 to number_of_all_nets (currently 105), which would give 5565 rules (only for the outer layers, inner layers have different spacing). 
I would like to suggest an integrated KiCAD function that allows to assign voltage potentials to the nets and spacing rules according to the voltage difference.
Until then, I let the most important rules lead to errors and check them all manually.<br>

Q:	&ensp;This is open source. Can I modify it? Can I sell it?<br>
A:	&ensp;Sure! But please use your own version numbering and change "Designed by Rootthecause" 
to "Designed by [Your Name] based on a design by Rootthecause". 
As this is licensed under CeRN OHL v2 Weakly Reciprocal, you must disclose the source, 
state changes and use the same license if used for non private projects.
Learn more about this here: https://choosealicense.com/licenses/cern-ohl-w-2.0/<br>

Q:	&ensp;I've got a question not listed here, can I contact you?<br>
A:	&ensp;Please use the [Discussions](https://github.com/Rootthecause/DCDC/discussions) on GitHub for techical related questions.<br> 

Q:	&ensp;Is there a way to support your projects?<br>
A:	&ensp;Yes, there are two ways: Sharing your findings and results of your own DCDC build as well was financial support for development of this and future projects: https://ko-fi.com/rootthecause<br>
&ensp;&ensp;&ensp; Thanks a lot!

Q: &ensp; I measure something weird [...]<br>
A: &ensp; Make sure that your measuring device is properly isolated. Sometimes small leakage currents can cause unwanted voltages, since we're woking with up to 600V. <br>
Also make sure to use a ground spring when working with an oscilloscope for measuring fast signals.<br>
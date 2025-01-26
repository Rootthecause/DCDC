
This file contains some additional info on the build guide.

Resin used: Liqcreate Flame Retardant HDT 
Link: https://www.liqcreate.com/supportarticles/flame-retardant-hdt-resin-3d/

Notes about shinkage:
The STL was designed without shinkage compensation. 
Liqcreate's Homepage states 100,65 % Shinkage for X and Y, and 100.50 for Z. 

Here are my own measurements just to check.

ETD39 Isolator
|                       |  X             | Y    | Z    |
|:---------------------:|:--------------:|:----:|:---:|
|Construction           |  41.00 mm      |15.00 | 6.00|
|Part before curing     |  40.93 mm      |15.10 | 6.18|
|Part 10 min curing     |  40.90 mm      |15.10 | 6.20|
|Part 20 min curing     |  40.88 mm      |15.11 | 6.22|
|Part 30 min curing     |  40.88 mm      |15.11 | 6.22|
||100,29%|99,27%|96,46%|

ETD39 Prim

|                       |  X             | d_innr | d_outr |
|:---------------------:|:--------------:|:----:|:----:|
|Construction           |  21.70 mm      |12.90 | 14.90|
|Part before curing     |  21.93 mm      |12.70 | 14.84|
|Part 10 min curing     |  21.91 mm      |12.69 | 14.82|
|Part 20 min curing     |  21.91 mm      |12.69 | 14.81|
|Part 30 min curing     |  21.90 mm      |12.69 | 14.80|
||99,09%|101,65%|100,68%|

ETD39 Sek

|                       |  X             | d_innr | d_outr |
|:---------------------:|:--------------:|:----:|:----:|
|Construction           |  7.00 mm       |12.90 | 14.90|
|Part before curing     |  7.14 mm *     |12.70 | 14.84|
|Part 10 min curing     |  7.20 mm       |12.71 | 14.79|
|Part 20 min curing     |  7.19 mm       |12.71 | 14.79|
|Part 30 min curing     |  7.18 mm       |12.70 | 14.78|
||97,49%|101,58%|100,81%|

*unclear what happened there

Transformer Window required: 28,7 mm 
Transformer Window measured: 29,2 mm 

## Conclusion
Somehow some values did not shrink. I believe that the orientation has influence on the shinkage.
But overall, Liqcreate's stated 100,65 % seems plausible. 
I've not conclued any further tests, since the first prints worked well.
Sanding of the flat end-surfaces is allowable if done prior to the isolation test.

## Pro-Tipps
- if you've got too many sticky nots as an promotional gift, use them to stirr your 2K-Epoxy on it. 
- use (left over) PTFE-Tube from a bowden 3D-Printer to stirr the Epoxy. When hardened, it can be easily removed from the tube and be reused.
- you can use hot air (e.g. from a solder station) to warm up deposited epoxy. When warmed, it removes air bubbles in the epoxy and lowers viscosity. This will result in nice surfaces even when the epoxy has started to harden. 
- lay the stirr-tube/rod in the rest of the epoxy. This will give you a good idea how hard the epoxy on the transformer is, without poking it.


Winding scheme:
- Primary (left half): 
Layer 1: 6 Windings
Layer 2: 5 Windings 
Layer 3: 3 Windings
- Primary (right half): 
Layer 1: 6 Windings
Layer 2: 5 Windings 
Layer 3: 4 Windings

- Secondaries:
- two inner winding (clockwise, it doesn't matter, as long as the other is the same way around)
- two outer windungs ontop of the inner windings. (clockwise)



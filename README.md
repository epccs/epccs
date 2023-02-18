# epccs

Hi, I am Ron. I am an electrical engineer working with LEDs, drivers, and related controls. Not so much microcontrolers at the moment (maybe a little.)

## LEDs

When an electron passes through a [P-N_junction], it releases energy, some turns into heat and some light. The amount of energy released is related to the semiconductor [band-gap] energy. Different semiconductors have different band gaps, so when a photon is emitted, its color can be roughly correlated with the band-gap energy of the P-N junction material. A trick some LEDs use is [phosphor-down] conversion to make a broader spectrum of light. [Luminous] efficacy continues improving; in other words, the ratio of photons to heat continues to improve.

[P-N_junction]: <https://en.wikipedia.org/wiki/P%E2%80%93n_junction>

[band-gap]: <https://en.wikipedia.org/wiki/Band_gap>

[phosphor-down]: <https://en.wikipedia.org/wiki/Phosphor>

[Luminous]: <https://en.wikipedia.org/wiki/Luminous_efficacy>

## Electromagnetic interference

I am no expert at [EMI], but I have been fighting with several designs for about a year. The LED drivers are [Buck], [Boost], and [Buck-Boost]. In each case, there are parts of the circuit where the current flow path changes abruptly, usually involving switches like MOSFETs but also sometimes diodes. The abrupt change is nearly a discontinuity, but a ramp can be seen looking close. A magnetic H field flairs around the path, experiencing the sudden current flow. The edge of everything metal near that will block the hi frequency H field by developing current eddies. The superposition theorem tells us that the net result of the induced current ends up on the outermost edge. A relation between frequency and skin depth is also at play, but let's keep it simple and ignore thin traces. So, we are concerned with how those edge currents can reach out along the edges of planes and induce currents elsewhere. We need to do the circuit board planes so they enclose the discontinuous paths, and those enclosing edges don't cross areas where they can induce knock-on effect current flow. That will minimize emissions, but putting a cage over the compartment where switching occurs is better. A [Near-Field Probe] might help chase things down but drawing the switching paths and thinking about them is what I did.

[EMI]: <https://en.wikipedia.org/wiki/Electromagnetic_interference>

[Buck]: <https://en.wikipedia.org/wiki/Buck_converter>

[Boost]: <https://en.wikipedia.org/wiki/Boost_converter>

[Buck-Boost]: <https://en.wikipedia.org/wiki/Buck%E2%80%93boost_converter>

[Near-Field Probe]: <https://www.langer-emv.de/en/product/rf-passive-30-mhz-3-ghz/35/rf1-set-near-field-probes-30-mhz-up-to-3-ghz/270>

## Electromagnetic compatibility

Immunity testing is another aspect of these darn LED drivers. Some of the specifications use a technique called Bulk Current Injection (BCI, like ISO 11452-4). I found a [culprit] for the parts not getting through this test after getting some BCI test equipment. I removed the structures that could act like a loop-gap resonator.

[culprit]: <https://en.wikipedia.org/wiki/Loop-gap_resonator>

Once the resonance grows large enough, the lights do some bizarre things. On the next iteration, it became clear that our microcontroller input had negligible immunity, but it worked fine on the bench. It is important if you don't want to burn cash to get some in-house [BCI] capability.

[BCI]: <https://www.fischercc.com/type/bulk-current-injection-probes/>

## Conducted Emissions

Conducted Emission has to do with measuring voltage and current on the wires to the unit and has taken the longest to understand. The wires are long, nearly 2 meters for some tests; the idea is to represent the wiring harness. The main thing that I needed to understand was that the floating wires (to toggle switch and ilk) are resonators with 1uH per meter and 10pF out at the floating end. They build up and store energy, so you have to figure out how to dampen it. Here are some links [Tacoma Narrows], [Wave Behavior]. The long wires with floating ends were also causing high E-field emissions because the entire 2-meter harness was placed on the table.

[Tacoma Narrows]: <https://en.wikipedia.org/wiki/Tacoma_Narrows_Bridge_(1940)>
[Wave Behavior]: <https://www.youtube.com/watch?v=DovunOxlY1k>

## Thanks for visiting

That is it for now. I hope to find some time for my own projects (they are more fun).

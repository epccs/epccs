# epccs

Hi, I am Ron. I am an electrical engineer working with LEDs, drivers, and related controls. Not so much microcontrolers at the moment (maybe a little.)

## LEDs

When an electron passes through a [P-N_junction], it releases energy, some turns into heat and some light. The amount of energy released is related to the semiconductor [band-gap] energy. Different semiconductors have different band gaps, so when a photon is emitted, its color can be roughly correlated with the band-gap energy of the P-N junction material. A trick some LEDs use is [phosphor-down] conversion to make a broader spectrum of light. [Luminous] efficacy continues improving; in other words, the ratio of photons to heat continues to improve.

[P-N_junction]: <https://en.wikipedia.org/wiki/P%E2%80%93n_junction>

[band-gap]: <https://en.wikipedia.org/wiki/Band_gap>

[phosphor-down]: <https://en.wikipedia.org/wiki/Phosphor>

[Luminous]: <https://en.wikipedia.org/wiki/Luminous_efficacy>

## Electromagnetic interference

I am no expert at [EMI], but I have been fighting with several designs for about a year. The LED drivers are [Buck], [Boost], and [Buck-Boost]. In each case there are parts of the circuit where current changes from continous to discontinous, continous is where it is ramping up and down, discontinous is where the ramp abrupbly goes to zero. Where discontinous current flow is occureing is the main contributor to EMI, this part of the circuit needs to be tight and compact. The discontinous part of the circuit also needs to be sourounded my a return path plane (i.e., ground).

[EMI]: <https://en.wikipedia.org/wiki/Electromagnetic_interference>

[Buck]: <https://en.wikipedia.org/wiki/Buck_converter>

[Boost]: <https://en.wikipedia.org/wiki/Boost_converter>

[Buck-Boost]: <https://en.wikipedia.org/wiki/Buck%E2%80%93boost_converter>

## Electromagnetic compatibility

Immunity testing is another aspect of these darn LED drivers. Some of the specifications use a technique called Bulk Current Injection (BCI, like ISO 11452-4). I found a [culprit] for the parts not getting through this test after getting some BCI test equipment. I removed the structures that could act like a loop-gap resonator. But the housing itself is still a problem.

[culprit]: <https://en.wikipedia.org/wiki/Loop-gap_resonator>

Once the resonance grows large enough the lights do some really strange things. I could see someone claming it had been possed. So if you are driving down the road some day and your lights (or other electronics) freak out, you are inside the beam of a radar.

## Thanks for visiting

That is it for now. I hope to find some time for projects.

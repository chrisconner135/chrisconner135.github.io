---
layout: page
title: Classical bulk acoustic resonator measurements
description: Measurements of hBAR devices of different materials and design variations.
img: assets/img/HBAR1.jpg
importance: 3
category: work
---

In my graduate school lab, our study of mechanical systems in the quantum regime had been primarily focused on surface acoustic wave systems. One of my projects in the lab has been to expand our toolbox to include bulk resonators, specifically high overtone bulk acoustic resonators (HBARs), to complement our surface acoustic wave devices. 

HBARs are an attractive system to complement our SAW devices for a number of reasons. With SAW devices, we have a large degree of engineerability in the coupling, with straightforward integration of tunable couplers and strong coupling up to tens of $$\mathrm{MHz}$$ readily achievable. On the other hand, achieving long lifetimes in surface acoustic wave systems is quite challenging. Typical lifetimes of surface acoustic wave resonators are order $$1~\mathrm{\mu s}$$. In contrast to these systems, HBAR resonators typically have much longer lifetimes of tens to hundreds of $$\mathrm{\mu s}$$, at the cost of coupling being more difficult to engineer, typical qubit-HBAR hybrid systems have couplings less than $$1~\mathrm{MHz}$$ and tunability is achieved by shifting the qubit frequency.

Typical HBAR devices consist of a piezoelectric transducer fabricated on a substrate such as silicon or sapphire. The substrate itself forms the resonator, with its polished top and bottom surfaces acting as mirrors. Typical material choices and device geometries lend themselves to devices with fundamental resonant modes in the range of about $$10~\mathrm{MHz}$$. To interface with our superconducting qubits, which operate at a few GHz, we study high overtones of these resonators which lie at these higher frequencies. 

Towards the goal of interfacing these resonators with our superconducting qubits, I fabricated and measured many devices with a range of designs and materials.

One material I investigated was bulk lithium niobate. Lithium niobate is an attractive option for these devices as it has a very strong piezoelectric response compared to most other materials that are used for HBARs. I fabricated devices with aluminum film deposited and patterned to form electrodes for room temperature measurements using a microwave probe station, as well as bond pads for wirebonding to sample boxes suited for cryogenic measurements down to $$10~\mathrm{mK}$$. A typical measurement of one of these devices looks like figure 1, which is a two-port transmission measurement through one of the HBAR transducers, taken at room temperature using a microwave probe station and VNA. In the data, we see transmission with repetitive features separated by the FSR of the device, in this case about $$7~\mathrm{MHz}$$.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/HBAR_ClearLNS21.png"
            title="Lithium niobate HBAR S21"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 1, room temperature S21 measurement of a lithium niobate HBAR device.
</div>

After wirebonding a device and mounting it in one of our adiabatic demagnetization refridgerators, I can do a careful transmission measurement around one of these modes and fit it to extract a measurement of the quality factor of one of these modes, shown here in figure 2.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/MMplot_20220324_Summer_ADRBAWv1NER3C4_100R_100R_nogp_scans53to72_Qfit_bigger_SD.png"
            title="Lithium niobate HBAR circle fit"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 2, circle fit of cryogenic measurement of a lithium niobate HBAR device.
</div>

Excitingly, these measurements show an internal quality factor above one million at $$3~\mathrm{GHz}$$, corresponding to an $$f\times q$$ product of $$4e15$$.

I also perform these transmission measurements and circle fits at a range of powers, down to the single phonon level. Results of these measurements for a selection of modes near typical qubit operating frequencies are shown here in figure 3. Importantly, many modes show internal Q's above one million in the single phonon regime, which is encouraging for potential qubit operation.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/MMplot_PowerSweep_ClearLN_legend_SD.png"
            title="Lithium niobate HBAR power sweep"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 3, cryogenic power sweep of a lithium niobate HBAR device.
</div>

Beyond bulk lithium niobate, I fabricated and tested devices on a range of substrates and stacks including thin film lithium niobate and aluminum nitride on silicon and sapphire substrates. When transitioning from a bulk piezo to a film piezoelectric, the thickness of the piezoelectric layer becomes an important factor to consider as there is a matching condition for the overtone modes where the piezo thickness must match an $$\frac{n+1}{2}$$ condition with the overtone wavelength. This can be seen in the data shown here in figure 4, from a device made with a $$1~\mu m$$ lithium niobate film on a silicon substrate. The first wavelength condition is met at $$1.7~\mathrm{GHz}$$, where the wavelength of the overtone mode is equal to $$2~\mathrm{\mu m}$$, twice the piezoelectric film thickness, and the second condition is met at $$5.4~\mathrm{GHz}$$, where the wavelength of the overtone mode is $$2/3$$ the piezoelectric film thickness. The upper panels of figure 4 are $$S_{21}$$ measurements of the transducers, stepped by the measured free spectral range of the device. Each dip shown in the upper panel is fit to extract the internal and coupled quality factor, which is plotted in the lower panels. The strongest coupling corresponds to the lowest $$Q_c$$, which agrees with the wavelength matching condition for the piezoelectric film where the minima of $$Q_c$$ align with modes at $$1.7~\mathrm{GHz}$$ and at $$5.4~\mathrm{GHz}$$.

<div class="row mt-3 justify-content-center">
    <div class="col-md-6">
        {% include figure.liquid
            loading="eager"
            path="assets/img/MMplot_2DFSR20241126_200umrad40umsep_scan15_Qfit.png"
            title="A"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
    <div class="col-md-6">
        {% include figure.liquid
            loading="eager"
            path="assets/img/MMplot_2DFSR20241126_200umrad40umsep_scan17_Qfit.png"
            title="B"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 4, room temperature multi-mode transmission scans and quality factors.
</div>

The main takeaway from this project is that we can make HBAR devices with strongly piezoelectric materials that maintain large internal quality factors, suggesting that there is a route to leverage the inherently long lifetimes from this type of mechanical resonator while being able to engineer strong coupling to superconducting qubits.

There is an additional observation that I made from making and testing these devices which I find very exciting. This observation came from my devices made from a $$900~\mathrm{nm}$$ aluminum nitride film on a silicon substrate. The majority of these devices had cryogenic internal quality factors in the range of $$6e5$$, good but not quite as good as some of the other materials I had tested. However, one of the devices I made where I varied the device geometry had modes with cryogenic internal quality factors of $$3.6e6$$ at single phonon level, which is a significant improvement over other devices in the same material and on par with the best devices of all the ones I made. This device was made in the same fabrication run as the other AlN on Si devices, with the only difference being its transducer geometry. While it wasn't part of a targeted design effort, these results suggest that through careful engineering of the transducer geometry the quality factors of these HBAR devices could be further improved.

I presented the results of these measurements at APS March Meeting in Denver Colorado, 2026.
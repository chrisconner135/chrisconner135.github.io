---
layout: page
title: Flip chip qubits
description: Measurements of superconducting qubits on galvanically separated flip-chip substrates.
img: assets/img/IMG_4585_SD.png
importance: 2
category: work
---

My second major project as a graduate student at UChicago consisted of coupling together two superconducting qubits on galvanically separate substrates. This was a natural continuation of my first project, which was assisting with the development of our novel flip-chip bonding process, described in {% cite satzinger2019 %}. That project developed our flip-chip bonding process, which is how we couple our superconducting qubit devices to our mechanical resonators with a facile process that is compatible with bespoke chip designs and materials. In that paper, we described the alignment and bonding process and then demonstrated a proof of principle experiment consisting of a set of hanging coplanar waveguide resonators located on the bonded flip-chip module, inductively coupled across the inter-chip gap to a feedline on the base chip. My continuation of that project was to take it into the quantum regime by placing an Xmon-style superconducting qubit on each of the two chips in the assembly. This work was published in APL {% cite conner2021 %}.

A circuit schematic for the device is shown here in figure 1 e. The elements on the top chip, including qubit two, its inductive coupler, and its readout resonator are shown inside the red box. This red box represents the top chip, outlined in red in figure 1 b. Figure 1 c shows a microscope photo of the fabricated top chip with its squid loop shown in the inset d. Figure 1 a shows a microscope image of the bottom chip with qubit one and its associated control and readout lines before flip-chip assembly. The location where the top chip will be bonded is represented by the dashed red box. Within this dashed red box, the flux control (purple), capacitively coupled drive line (orange), and qubit coupling line (green) are visible. Flux and qubit coupling are achieved inductively while the drive is achieved capacitively.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/QFC_fig1.png"
            title="Flip chip qubit assembly"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 1, device overview.
</div>

I performed standard qubit bringup and characterization of both qubits. Their parameters were in line with typical qubits of this design we were making in the lab at the time. These measured parameters are summarized here in table 1.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/QFC_table1.png"
            title="Measured qubit parameters"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Table 1, qubit parameters.
</div>

Once the single-qubit parameters have been measured, the next task was randomized benchmarking of single qubit gates. This involves interleaving the gates with a random Clifford gate sequence and comparing to a benchmark consisting of only a randomized sequence. This technique allows for benchmarking of the gates themselves, independent of surface preparation and measurement errors. This benchmarking, shown below, revealed that all single qubit gates had better than 99% fidelity.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/QFC_singlequbitrb.png"
            title="Single qubit gate randomized benchmarking"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 2, randomized benchmarking of single qubit gates.
</div>

Now that I have shown good control of single qubit rotations, we can expore interactions between the two qubits. The most straightforward way to enact an interaction is by tuning the frequencies of the qubits using their inductively coupled flux lines to bring them on resonance with each other. Once they are on resonance, they can exchange energy in an iswap interaction. I demonstrate see these swaps by first exciting qubit one with a pi pulse, and then sweeping the duration of flux tuning pulses on the qubits. The pulse sequence and resulting data are shown in figure 3 a.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/QFC_bellfig.png"
            title="Single qubit swap and bell state"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 3, two-qubit swaps and bell state tomography.
</div>

After the two qubit resonant interaction, I perform a set of single qubit rotations followed by two qubit readout to measure the density matrix of the system. Density matrices of the system at three significant points are shown in figure 3 b, c, and d. Figure 3 b is the density matrix of the system upon initialization with a pi pulse on qubit one, the largest element of the density matrix shows we are in the $$\lvert eg \rangle$$ state as expected. Figure 3 c is the density matrix of the system after a full swap with a pulse duration of about 22 ns, where now the largest element of $$\rho$$ suggests we are in the $$\lvert ge \rangle$$ state, with some increase in the ground state elements due to $$T_1$$ decay. I can create an entangled bell state $$(\lvert ge \rangle-\lvert eg \rangle)/\sqrt{2}$$, by instead truncating the swap pulse halfway at around 11 ns. I plot the measured density matrix for this state in figure 3 d. The fidelity of these three denstity matrices, calculated as trace distance to the ideal state are $$96\%$$, $$94\%$$, and $$95\%$$ respectively.

Beyond the iswap gate, there is another significant two-qubit entangling gate that can be realized with this system. That is the controlled-Z (cz) gate. As a result of a cz gate, the $$\lvert ee \rangle$$ state acquires a relative phase of $$\pi$$ and all other states are left as is. This can also be conceptualized as a phase being applied to one qubit, conditional on the other qubit being in its excited state. To realize this gate, we can leverage a higher level transition of the system, between the $$\lvert fg \rangle$$ state and the $$\lvert ee \rangle$$ state. This transition is circled in red in figure 4 a.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/QFC_cz.png"
            title="System eigenstates and controlled z gate"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 4, qubit spectroscopy and controlled z gate .
</div>

In order to locate this transition in parameter space, I perform two tone spectroscopy at large enough powers to reveal higher excitation number eigenstates of the system through multi-photon processes. This spectroscopy is shown in figure 4 a, verified through simulation overlayed in the black dashed lines. We can build the cz gate step by step by following figures 4 b, c, and d. First with figure 4 b, I perform a Ramsey style experiment on qubit 2 with two $$\pi$$ pulses, varying the phase of the second pulse to produce the data shown. I perform this measurement both with qubit one in its ground and excited state as a control. Next, with the pulse sequence shown in figure 4 c, I use flux pulses to bring the system into its $$\lvert ee \rangle \leftrightarrow \lvert fg \rangle$$ transition for an amount of time (about 30 ns in this case) required for a full swap from $$\lvert ee \rangle$$ to $$\lvert fg \rangle$$ and back, acquiring a phase of $$\pi$$. This is visible in the Ramsey experiment as a $$\pi$$ shift between the blue and red data, showing that the relative phase is only acquired if the control qubit was initialized in its excited state. In this data, one can also notice that a global phase was acquired by both qubit as the flux pulses change the frequency of the system during the duration of the gate. In quantum processors, it is typically unnecessary to correct for global phase of individual gates, but it is straightforward to do so by including a short, second detuning pulse after the main gate pulse. This pulse sequence and resulting Ramsey data are shown in figure 4 d.

I benchmark the quality of the cz gate using two methods. Firstly with randomized benchmarking, following a similar technique as shown above for the single qubit gates in figure 2, but expanded to the two qubit case. Benchmarked in this manner we find a gate fidelity of $$94\%$$, shown here in figure 5.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/QFC_czrb.png"
            title="CZ gate randomized benchmarking"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 5, two-qubit randomized benchmarking of the controlled z gate.
</div>

An alternate way to benchmark the gate is to perform quantum process tomography. In this technique we measure the density matrix of the system with the cz gate and the set of Pauli operators applied. We can then calculate the $$\chi$$ matrix according to $$\epsilon(\rho)=\Sigma_{mn}\tilde{E}_m\rho\tilde{E}^\dagger_n\chi_{mn}$$, where $$\rho$$ is the input density matrix, $$\epsilon(\rho)$$ is the output density matrix, and $$\tilde{E}$$ is from the set of Pauli operators. The resulting $$\chi$$ matrix is shown here in figure 6. Using this process tomography we calculate the fidelity of the gate as trace distance to the ideal $$\chi$$ matrix to be $$95\%$$.

<div class="row mt-3 justify-content-center">
    <div class="col-md-10" style="max-width: 75%;">
        {% include figure.liquid
            loading="eager"
            path="assets/img/QFC_chi_SD.png"
            title="CZ gate chi matrix"
            class="img-fluid rounded z-depth-1"
            zoomable=true
        %}
    </div>
</div>
<div class="caption text-center">
    Figure 6, quantum process tomography chi matrix of the controlled Z gate.
</div>

{% bibliography --cited --group_by none %}

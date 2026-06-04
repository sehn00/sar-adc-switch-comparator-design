# SAR ADC Switch and Comparator Design

Design and Comparative Analysis of Bootstrapped Sampling Switch and StrongARM-Based Comparator for a 6-bit, 10-MS/s SAR ADC in 500 nm CMOS Technology

[📄 Paper](./paper.pdf) | [🖼 Poster](./poster.pdf)

---

## 프로젝트 요약

본 프로젝트는 중앙대학교 전자전기공학부 CMOS 집적회로 설계 과목의 팀 프로젝트로, 500 nm CMOS 공정을 기반으로 6-bit, 10-MS/s SAR ADC의 핵심 아날로그 블록인 Bootstrapped Sampling Switch와 Comparator를 설계하고 성능을 비교·분석한 연구이다.

Bootstrapped Sampling Switch에서는 3-stack NMOS sizing, MOSFET body connection, bootstrap capacitor 크기가 회로 특성에 미치는 영향을 분석하였다. Comparator에서는 Type-I, Type-II, Type-III 세 가지 후보 구조를 설계하고 propagation delay, transition speed, average power, minimum resolvable input 및 output-holding 특성을 비교하였다.

비교 결과를 바탕으로 Type-III output-holding StrongARM dynamic latch comparator를 최종 구조로 선정하였으며, 본 저장소에는 대한전자공학회 하계학술대회 제출 논문 및 포스터 자료가 포함되어 있다.

---

## Authors

Wooseok Choi
Jongwoo Seo
Taekgeun Kim
Jiyeon Lee
Kwanwoo Kim
Yun Heo
Sehyeon Choi
Junhyung Park

Department of Electrical and Electronics Engineering
Chung-Ang University

---

## Project Scope

### Bootstrapped Sampling Switch

* 3-stack NMOS width sweep
* MOSFET body connection analysis
* Bootstrap capacitor sweep
* OUT-node glitch behavior analysis
* Boost-node voltage evaluation

### Comparator Architectures

* Type-I : Static Comparator + SR Latch
* Type-II : StrongARM Dynamic Comparator + NAND-Based SR Latch
* Type-III : StrongARM Dynamic Comparator + Output-Holding Latch

### Evaluation Metrics

* Propagation Delay
* Rise Time
* Fall Time
* Average Power
* Minimum Resolvable Input
* Output-Holding Behavior

All results were obtained through schematic-level transient simulations.

---

## Key Results

### Bootstrapped Sampling Switch

* Output-side NMOS sizing significantly affected OUT-node behavior.
* The final NMOS transistor (W₃) showed the strongest impact on MAX VOUT.
* Approximately 10 V boost-node voltage was achieved with a 143 pF bootstrap capacitor.

### Comparator Performance Comparison

| Metric                   |   Type-I |  Type-II |  Type-III |
| ------------------------ | -------: | -------: | --------: |
| Propagation Delay        | 1.060 ns | 1.084 ns | 0.9829 ns |
| Rise Time                | 473.2 ps | 444.1 ps |    286 ps |
| Fall Time                | 300.4 ps | 261.2 ps |  107.8 ps |
| Average Power            | 951.8 µW | 290.3 µW |  327.6 µW |
| Minimum Resolvable Input |    14 mV |    13 mV |     22 µV |

### Final Comparator Selection

Type-III was selected considering the trade-off among propagation delay, transition speed, average power, minimum resolvable input, and output-holding capability.

---

## Repository Contents

| File       | Description         |
| ---------- | ------------------- |
| paper.pdf  | Conference paper    |
| poster.pdf | Poster presentation |

---

## Limitations

This work is based on schematic-level transient simulations.

The following analyses were not included in this study:

* Post-layout parasitic extraction
* Process, Voltage, and Temperature (PVT) variation
* Device mismatch analysis
* Monte Carlo simulation
* ADC-level metrics such as DNL, INL, SNDR, ENOB, and FoM

---

## Future Work

* Integration with SAR Logic and CDAC
* Full SAR ADC verification
* Post-layout simulation
* PVT variation analysis
* Device mismatch analysis
* Monte Carlo simulation
* ADC-level performance evaluation

---

## Conference

The Institute of Electronics and Information Engineers (IEIE)
2026 Summer Conference

---

## Citation

If you use or reference this work, please cite the original conference paper included in this repository.

# SAR ADC Switch and Comparator Design

Design and Comparative Analysis of Bootstrapped Sampling Switch and StrongARM-Based Comparator for a 6-bit, 10-MS/s SAR ADC in 500 nm CMOS Technology

[📄 Paper](./sar_adc_paper.pdf) | [🖼 Poster](./sar_adc_poster.pdf)

---

## 프로젝트 요약

본 프로젝트는 중앙대학교 반도체설계특성화사업의 지원을 받아 전자전기공학부에서 수행한 CMOS 집적회로 설계 팀 프로젝트이다. 500 nm CMOS 공정을 기반으로 6-bit, 10-MS/s SAR ADC에 적용할 Bootstrapped Sampling Switch와 Comparator를 설계하고, 각 블록의 회로 구조와 주요 설계 변수가 동작 특성에 미치는 영향을 schematic-level transient simulation을 통해 분석하였다.

Bootstrapped Sampling Switch에서는 입력 전압 변화에 따른 MOS switch의 ON 저항 변동을 완화하고 sampling 안정성을 확보하기 위해 출력단에 3-stack NMOS 구조를 적용하였다. 이후 NMOS sizing, MOSFET body connection, bootstrap capacitor 크기를 변화시키며 OUT node의 transient behavior와 boost node 전압 특성을 비교하였다.

Comparator에서는 SAR ADC의 bit decision 성능을 검토하기 위해 Type-I, Type-II, Type-III 세 가지 후보 구조를 구현하였다. 각 구조는 propagation delay, rise/fall time, average power, minimum resolvable input, output-holding 특성을 기준으로 비교하였으며, 단순한 동작 속도뿐 아니라 전력 소모와 입력 전압 구분 능력, 출력 유지 특성 사이의 trade-off를 함께 분석하였다.

본 연구는 개별 아날로그 블록 수준의 schematic-level 검증을 중심으로 수행되었다. 향후에는 SAR logic 및 CDAC를 결합한 전체 SAR ADC 회로를 구성하고, post-layout parasitic, PVT variation, device mismatch를 포함한 조건에서 변환 정확도와 동작 안정성을 검증할 예정이다.

---

## Authors

Woosuk Choi, Sehyeon Choi, Jiyeon Lee, Yun Heo,

Jongwoo Seo, Kwanwoo Kim, Taekgeun Kim, and Junhyung Park

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

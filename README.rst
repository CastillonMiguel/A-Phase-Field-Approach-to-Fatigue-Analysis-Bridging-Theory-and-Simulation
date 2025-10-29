A Phase-Field Approach to Fatigue Analysis: Bridging Theory and Simulation
==========================================================================

.. image:: https://raw.githubusercontent.com/CastillonMiguel/DocTester/main/docs/source/_static/logo_name.png
   :target: https://doctesterdoc.readthedocs.io/en/latest/
   :alt: A Phase-Field Approach to Fatigue Analysis: Bridging Theory and Simulation

.. image:: https://readthedocs.org/projects/DocTesterDoc/badge/?version=latest
    :target: https://doctesterdoc.readthedocs.io/en/latest/
    :alt: Documentation Status

Repository code
---------------
The code in this repository is the same version used for the paper. For a more visual and faster experience we recommend using the generated documentation, which provides interactive views and graphs: `Documentation and interactive views <https://doctesterdoc.readthedocs.io/en/latest/>`_.

Overview
--------
This  article presents a novel, robust and efficient framework for fatigue crack-propagation that combines the principles of Linear Elastic Fracture Mechanics (LEFM) with phase-field fracture (PFF). Contrary to cycle-by-cycle PFF approaches, this work relies on a single simulation and uses standard crack propagation models such as Paris' law for the material response, simplifying its parametrization.
The core of the methodology is the numerical evaluation of the derivative of a specimen's compliance with respect to the crack area. To retrieve this compliance the framework relies on a PFF-FEM simulation, controlled imposing a monotonic crack growth. This control of the loading process is done by a new crack-control scheme which allows to robustly trace the complete equilibrium path of a crack, capturing complex instabilities. The specimen's compliance obtained from the PFF simulation enables the integration of Paris' law to predict fatigue life.

The proposed methodology is first validated through a series of benchmarks with analytical solutions to demonstrate its accuracy. The framework is then applied to more complex geometries where the crack path is unknown, showing a very good agreement with experimental results of both crack paths and fatigue life.

.. highlights::

   - **Develops a phase-field framework** for fracture and fatigue analysis.
   - New Energy-Controlled Solvers: It introduces two new, efficient solvers (variational and non-variational) that can simulate the entire fracture process, including complex behaviors like snap-back, in a single run.
   - Efficient Fatigue Analysis: The framework uses the results from a single quasi-static simulation to predict fatigue life based on Paris' law, avoiding the need for computationally expensive cycle-by-cycle simulations.
   - Improved Accuracy: It includes a validated method to correct for the overestimation of crack length that is common in phase-field models, leading to results that align well with established theoretical solutions (LEFM).
   - Complex Geometries: The method is successfully applied to complex specimens with holes where the crack path is unknown beforehand, demonstrating its ability to predict intricate crack trajectories that match experimental data.
   - Open-Source and Reproducible: The entire toolchain, including the PhaseFieldX library and all simulation scripts, is open-source to ensure full reproducibility of the findings.

This repository is designed to ensure complete reproducibility of the results by providing all simulation data, parameter sets, meshes, and detailed numerical configurations.

.. code:: latex

    @misc{castillon2025,
        title={A Phase-Field Approach to Fracture and Fatigue Analysis: Bridging Theory and Simulation}, 
        author={M. Castillón and I. Romero and J. Segurado},
        year={2025},
        eprint={2509.08939},
        archivePrefix={arXiv},
        primaryClass={cond-mat.mtrl-sci},
        url={https://arxiv.org/abs/2509.08939}, 
    }

PhaseFieldX
-----------
All simulations in this work were produced with the open-source PhaseFieldX package.
Implementation details, examples and the API documentation can be found at:

- Project repository: `PhaseFieldX on GitHub <https://github.com/CastillonMiguel/phasefieldx>`_
- Documentation: `PhaseFieldX documentation <https://phasefieldx.readthedocs.io>`_
- Software paper (JOSS): `Castillón et al., JOSS (doi:10.21105/joss.07307) <https://doi.org/10.21105/joss.07307>`_

See the repository examples and the documentation for instructions to reproduce the simulations and to inspect the model implementations.
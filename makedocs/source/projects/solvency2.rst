.. module:: solvency2

.. _project_solvency2:

Project **solvency2**
=====================

.. include:: /banners.rst
   :start-after: Begin modelx badge
   :end-before: End modelx badge

|modelx badge|

**solvency2** is a project for building a model to
calculate life risks of selected policies at various points in their policy periods
based on Solvency II standard formula.
This project serves as a reference for
building models that contain complex nested projections.

Overview
--------

The model included in this project is named ``solvency2``.
The model calculates the capital requirement for life underwriting risk
based on Solvency II standard formula by policy and duration.

The overall capital requirement for life underwriting risk,
expressed as :math:`SCR_{life}`, is calculated by aggregating life sub-risks,
using a correlation matrix.

Each life sub-risk, as defined in the reference below, is defined
as the difference in net asset value under the base (best estimate) scenario
and the deterministic scenario with a prescribed stress on the risk factor,
except for Lapse risk.
For Lapse risk, three ("up", "down", "mass") scenarios are considered.

The model contains a parametric space
:mod:`SCR_Life[t0, PolicyID, ScenID] <solvency2.model.SCR_life>`.
:func:`~solvency2.model.SCR_life.SCR_life` cells in each ``SCR_Life[t0, PolicyID, ScenID]``
holds the value of Life underwriting risk at time ``t0`` for ``PolicyID``
and ``ScenID`` (1 by default), calculated based on
the solvency capital requirement standard formula under Solvency II.


References:
    * `COMMISSION DELEGATED REGULATION (EU) 2015/35 of 10 October 2014 <https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32015R0035>`_
    * `Solvency II Technical Specifications <https://wayback.archive-it.org/org-1495/20191229100044/https:/eiopa.europa.eu/regulation-supervision/insurance/solvency-ii/solvency-ii-technical-specifications>`_


Model Structure
---------------

Composition Structure
^^^^^^^^^^^^^^^^^^^^^

.. figure:: /images/projects/solvency2/composition.png

Inheritance Structure
^^^^^^^^^^^^^^^^^^^^^

.. figure:: /images/projects/solvency2/inheritance.png

Space Details
-------------

.. autosummary::
   :toctree: generated/
   :template: llmodule.rst

   ~model.Assumptions
   ~model.BaseProj
   ~model.Economic
   ~model.LifeTable
   ~model.Override.Expense
   ~model.Override.Lapse
   ~model.Override.LapseMass
   ~model.Override.Mortality
   ~model.SCR_life.Projection
   ~model.Policy
   ~model.PV
   ~model.SCR_life


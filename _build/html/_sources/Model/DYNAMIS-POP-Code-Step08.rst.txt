Step 8: The Micro-Simulation Implementation of a Cohort-Component Model
=======================================================================

Model Description
-----------------

.. include:: Step08/code/model_info.mpp
   :start-after: NOTE(model, EN)
   :end-before: */

.. figure:: Figures/Step08_Tables.png

   *Figure: The complete micro-simulation implementation of a cohort-component model*

The Updated Collection of Tables: TablesPopulation.mpp
------------------------------------------------------

.. include:: Step08/code/TablesPopulation.mpp
   :start-after: NOTE(TablesPopulation, EN)
   :end-before: */

.. include:: Step08/code/TablesPopulation.mpp
   :start-after: */
   :code:

Adding Districts in MicroDataOutput.mpp
------------------------------------------------------

The state district_nat is added to the list of output variables and the header row of micro-data output.

.. include:: Step08/code/MicroDataOutput.mpp
   :start-after: //DOCU08
   :end-before: //ENDDOCU08
   :code:

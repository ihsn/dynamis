Step 7: Base Immigration
========================

Model Description
-----------------

.. include:: Step07/code/model_info.mpp
   :start-after: NOTE(model, EN)
   :end-before: */

The new module: ImmigrationAgeSexDistrict.mpp
---------------------------------------------

.. include:: Step07/code/ImmigrationAgeSexDistrict.mpp
   :start-after: NOTE(ImmigrationAgeSexDistrict, EN)
   :end-before: */

.. include:: Step07/code/ImmigrationAgeSexDistrict.mpp
   :start-after: */
   :code:

Changes in the Simulation() function in model_core.mpp
------------------------------------------------------

The immigrant population is created in the Start() function after the starting file population is created and weights are calculated.

.. include:: Step07/code/model_core.mpp
   :start-after: ADD07
   :end-before: //ENDADD07
   :code:

Changes in the Start() function in PersonCore.mpp
-------------------------------------------------

The states of the immigrant actors have to be initialized in the Start() function. Most characteristics are sampled from the parameter tables.

.. include:: Step07/code/PersonCore.mpp
   :start-after: ADD07
   :end-before: //ENDADD07
   :code:

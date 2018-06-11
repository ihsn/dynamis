Step 5: Base Migration
======================

Model Description
-----------------

.. include:: Step05/code/model_info.mpp
   :start-after: NOTE(model, EN)
   :end-before: */

The new module: MigrationAgeSex.mpp
-----------------------------------

.. include:: Step05/code/MigrationAgeSex.mpp
   :start-after: NOTE(MigrationAgeSex, EN)
   :end-before: */

.. include:: Step05/code/MigrationAgeSex.mpp
   :start-after: */
   :code:

Update of the Start() function in PersonCore.mpp
------------------------------------------------

The Start() function is updated in order to initialize the new state for district of residence (district_nat).

.. include:: Step05/code/PersonCore.mpp
   :start-after: INCLUDE05
   :end-before: ENDINCLUDE05
   :code:

Declaration of the List of Districts in _CountryContext.mpp
-----------------------------------------------------------

As the number and names of districts is country-specific, it is declared in the module _CountryContext.mpp.

.. include:: Step05/code/_CountryContext.mpp
   :start-after: INCLUDE05
   :end-before: ENDINCLUDE05
   :code:

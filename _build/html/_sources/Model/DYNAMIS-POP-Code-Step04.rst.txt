Step 4: Base Fertility
======================

Model Description
-----------------

.. include:: Step04/code/model_info.mpp
   :start-after: NOTE(model, EN)
   :end-before: */

The new module: FertilityAgeTFR.mpp
-----------------------------------

.. include:: Step04/code/FertilityAgeTFR.mpp
   :start-after: NOTE(FertilityAgeTFR, EN)
   :end-before: */

.. include:: Step04/code/FertilityAgeTFR.mpp
   :start-after: */
   :code:

Update of the Start() function in PersonCore.mpp
------------------------------------------------

The Start() function is updated in order to initialize all states at the birth of a baby born in the simulation. In this case values do not come from the starting popiulation file but have to be derived otherwise, e.g. by accessing mother's characteristics (e.g. for setting the time) or by sampling (e.g. sex according to a parameter for sex ratio).

.. include:: Step04/code/PersonCore.mpp
   :start-after: INCLUDE04
   :end-before: ENDINCLUDE04
   :code:
   

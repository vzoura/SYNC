```abap
*&---------------------------------------------------------------------*
*& Include ZCL1R25996TOP                            - Report ZCL1R25996
*&---------------------------------------------------------------------*
REPORT zcl1r25996 MESSAGE-ID zcl1msg25.

*************************************
* Tables
*************************************
TABLES : cskt, cepct, ztbox_25_01, bkpf.

*************************************
* TABSTRIP
*************************************
CONTROLS gc_tab TYPE TABSTRIP.

DATA : gv_subscreen TYPE sy-dynnr.

*************************************
* Class Instance
*************************************
DATA : go_cont1 TYPE REF TO cl_gui_custom_container,
       go_alv1  TYPE REF TO cl_gui_alv_grid,
       go_cont2 TYPE REF TO cl_gui_custom_container,
       go_alv2  TYPE REF TO cl_gui_alv_grid.

*************************************
* Itab and wa
*************************************
DATA : BEGIN OF gs_cskt,
         kokrs TYPE cskt-kokrs,
         kostl TYPE cskt-kostl,
         datbi TYPE cskt-datbi,
         ktext TYPE cskt-ktext,
       END OF gs_cskt,
       gt_cskt LIKE TABLE OF gs_cskt.

DATA : BEGIN OF gs_cepct,
         prctr TYPE cepct-prctr,
         datbi TYPE cepct-prctr,
         kokrs TYPE cepct-kokrs,
         ktext TYPE cepct-ktext,
       END OF gs_cepct,
       gt_cepct LIKE TABLE OF gs_cepct.

DATA : gs_box type ztbox_25_01,
       gt_box TYPE TABLE OF ztbox_25_01.

*************************************
* For ALV
*************************************
DATA : gs_fcat1 TYPE lvc_s_fcat,
       gt_fcat1 TYPE lvc_t_fcat,
       gs_fcat2 TYPE lvc_s_fcat,
       gt_fcat2 TYPE lvc_t_fcat.

DATA : gs_variant TYPE disvariant,
       gs_layo    TYPE lvc_s_layo.

*************************************
* Common Variable
*************************************
DATA : gv_okcode TYPE sy-ucomm.

----------------------------------------------------------------------------------
Extracted by Direct Download Enterprise version 1.3.1 - E.G.Mellodew. 1998-2005 UK. Sap Release 758

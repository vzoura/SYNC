```abap
*&---------------------------------------------------------------------*
*& Include ZRC1_25_01TOP                            - Report ZRC1_25_01
*&---------------------------------------------------------------------*
REPORT zrc1_25_01 MESSAGE-ID zcl1msg25.

*************************************
* Tables
*************************************
TABLES : ztc1_docu_25.

*************************************
* Class Instance
*************************************
DATA : go_cont TYPE REF TO cl_gui_docking_container,
       go_alv  TYPE REF TO cl_gui_alv_grid.

*************************************
* Itab and wa
*************************************
DATA : BEGIN OF gs_body.
         INCLUDE STRUCTURE ztc1_docu_25.
DATA :   cell_tab TYPE lvc_t_styl,
         modi_yn,
       END OF gs_body,
       gt_body LIKE TABLE OF gs_body.

DATA : gs_delt TYPE ztc1_docu_25,
       gt_delt TYPE TABLE OF ztc1_docu_25.

*************************************
* For ALV
*************************************
DATA : gs_fcat    TYPE lvc_s_fcat,
       gt_fcat    TYPE lvc_t_fcat,
       gs_layo    TYPE lvc_s_layo,
       gs_variant TYPE disvariant.

DATA : gs_button TYPE stb_button.

*************************************
* Common Variable
*************************************
DATA : gv_okcode TYPE sy-ucomm,
       gv_mode   VALUE 'E'. "E : ####, D : ####

----------------------------------------------------------------------------------
Extracted by Direct Download Enterprise version 1.3.1 - E.G.Mellodew. 1998-2005 UK. Sap Release 758

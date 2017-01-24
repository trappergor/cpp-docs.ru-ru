---
title: "Directives Reference | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Directives Reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), directives reference"
ms.assetid: da6efcd1-18f7-41de-81cd-a002a02f9a22
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**x64**  
  
||||  
|-|-|-|  
|[.ALLOCSTACK](../Topic/.ALLOCSTACK.md)|[.ENDPROLOG](../Topic/.ENDPROLOG.md)|[Proc](../../assembler/masm/proc.md)|  
|[.PUSHFRAME](../../assembler/masm/dot-pushframe.md)|[.PUSHREG](../Topic/.PUSHREG.md)|[.SAVEREG](../../assembler/masm/dot-savereg.md)|  
|[.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)|[.SETFRAME](../../assembler/masm/dot-setframe.md)||  
  
### Метки кода  
  
|||  
|-|-|  
|[Выровнять](../../assembler/masm/align-masm.md)|[ДАЖЕ](../../assembler/masm/even.md)|  
|[МЕТКА](../../assembler/masm/label-masm.md)|[Орг.](../../assembler/masm/org.md)|  
  
### Условное сборка  
  
||||  
|-|-|-|  
|[ELSE](../Topic/ELSE%20\(MASM\).md)|[ELSEIF](../../assembler/masm/elseif-masm.md)|[ELSEIF2](../../assembler/masm/elseif2.md)|  
|[IF](../../assembler/masm/if-masm.md)|[IF2](../../assembler/masm/if2.md)|[IFB](../../assembler/masm/ifb.md)\/[IFNB](../../assembler/masm/ifnb.md)|  
|[IFDEF](../../assembler/masm/ifdef.md)\/[IFNDEF](../../assembler/masm/ifndef.md)|[IFDIF](../../assembler/masm/ifdif.md)\/[IFDIF &#91;&#91;I&#93;&#93;](../../assembler/masm/ifdif.md)|[IFE](../../assembler/masm/ife.md)|  
|[IFIDN](../../assembler/masm/ifidn.md)\/[IFIDN &#91;&#91;I&#93;&#93;](../../assembler/masm/ifidn.md)|||  
  
### Условное поток управления  
  
||||  
|-|-|-|  
|[.BREAK](../../assembler/masm/dot-break.md)|[.CONTINUE](../Topic/.CONTINUE.md)|[.ELSE](../../assembler/masm/dot-else.md)|  
|[.ELSEIF](../Topic/.IF.md)|[.ENDIF](../../assembler/masm/dot-endif.md)|[.ENDW](../../assembler/masm/dot-endw.md)|  
|[.IF](../Topic/.IF.md)|[.REPEAT](../../assembler/masm/dot-repeat.md)|[.UNTIL](../../assembler/masm/dot-until.md)|  
|[.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)|[.WHILE](../../assembler/masm/dot-while.md)||  
  
### Условное ошибка  
  
||||  
|-|-|-|  
|[.err](../../assembler/masm/dot-err.md)|[.ERR2](../../assembler/masm/dot-err2.md)|[.ERRB](../Topic/.ERRB.md)|  
|[.ERRDEF](../../assembler/masm/dot-errdef.md)|[.ERRDIF](../Topic/.ERRDIF]].md)\/[.ERRDIF &#91;&#91;I&#93;&#93;&#93;](../Topic/.ERRDIF]].md)|[.ERRE](../../assembler/masm/dot-erre.md)|  
|[.ERRIDN](../../assembler/masm/dot-erridn.md)\/[.ERRIDN &#91;&#91;I&#93;&#93;](../../assembler/masm/dot-erridn.md)|[.ERRNB](../Topic/.ERRNB.md)|[.ERRNDEF](../../assembler/masm/dot-errndef.md)|  
|[.ERRNZ](../../assembler/masm/dot-errnz.md)|||  
  
### Распределение данных  
  
||||  
|-|-|-|  
|[Выровнять](../../assembler/masm/align-masm.md)|[byte](../../assembler/masm/byte-masm.md)\/[sbyte](../../assembler/masm/sbyte-masm.md)|[dword](../../assembler/masm/dword.md)\/[SDWORD](../../assembler/masm/sdword.md)|  
|[ДАЖЕ](../../assembler/masm/even.md)|[FWORD](../Topic/FWORD.md)|[МЕТКА](../../assembler/masm/label-masm.md)|  
|[Орг.](../../assembler/masm/org.md)|[8 байт](../../assembler/masm/qword.md)|[REAL4](../../assembler/masm/real4.md)|  
|[REAL8](../Topic/REAL8.md)|[REAL10](../Topic/REAL10.md)|[TBYTE](../../assembler/masm/tbyte.md)|  
|[WORD](../../assembler/masm/word.md)\/[ШПАГА](../Topic/SWORD.md)|||  
  
### Равно  
  
||  
|-|  
|[\=](../../assembler/masm/equal.md)|  
|[EQU](../../assembler/masm/equ.md)|  
|[TEXTEQU](../../assembler/masm/textequ.md)|  
  
### Перечислить элемент управления  
  
||||  
|-|-|-|  
|[.CREF](../Topic/.CREF.md)|[.LIST](../Topic/.LIST.md)|[.LISTALL](../../assembler/masm/dot-listall.md)|  
|[.LISTIF](../../assembler/masm/dot-listif.md)|[.LISTMACRO](../../assembler/masm/dot-listmacro.md)|[.LISTMACROALL](../../assembler/masm/dot-listmacroall.md)|  
|[.NOCREF](../../assembler/masm/dot-nocref.md)|[.NOLIST](../../assembler/masm/dot-nolist.md)|[.NOLISTIF](../../assembler/masm/dot-nolistif.md)|  
|[.NOLISTMACRO](../../assembler/masm/dot-nolistmacro.md)|[Страница](../../assembler/masm/page.md)|[Подзаголовок](../../assembler/masm/subtitle.md)|  
|[.TFCOND](../../assembler/masm/dot-tfcond.md)|[НАЗВАНИЕ](../../assembler/masm/title.md)||  
  
### Макросы  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[EXITM](../../assembler/masm/exitm.md)|[GOTO](../../assembler/masm/goto-masm.md)|  
|[ЛОКАЛЬНАЯ](../Topic/LOCAL%20\(MASM\).md)|[Макроопределение](../Topic/MACRO.md)|[ПРОДУВКА](../../assembler/masm/purge.md)|  
  
### Прочее  
  
||||  
|-|-|-|  
|[ALIAS](../../assembler/masm/alias-masm.md)|[TAKE](../../assembler/masm/assume.md)|[ПРИМЕЧАНИЕ](../../assembler/masm/comment-masm.md)|  
|[ЭХО](../../assembler/masm/echo.md)|[END](../../assembler/masm/end-masm.md)|[.FPO](../Topic/.FPO.md)|  
|[INCLUDE](../../assembler/masm/include-masm.md)|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[MMWORD](../../assembler/masm/mmword.md)|  
|[ПАРАМЕТР](../../assembler/masm/option-masm.md)|[POPCONTEXT](../../assembler/masm/popcontext.md)|[PUSHCONTEXT](../../assembler/masm/pushcontext.md)|  
|[.RADIX](../../assembler/masm/dot-radix.md)|[.SAFESEH](../Topic/.SAFESEH.md)|[XMMWORD](../../assembler/masm/xmmword.md)|  
|[YMMWORD](../../assembler/masm/ymmword.md)|||  
  
### Процедуры  
  
||||  
|-|-|-|  
|[ENDP](../../assembler/masm/endp.md)|[INVOKE](../../assembler/masm/invoke.md)|[Proc](../../assembler/masm/proc.md)|  
|[PROTO](../../assembler/masm/proto.md)|||  
  
### Процессор  
  
||||  
|-|-|-|  
|[.386](../Topic/.386.md)|[.386P](../../assembler/masm/dot-386p.md)|[.387](../../assembler/masm/dot-387.md)|  
|[.486](../../assembler/masm/dot-486.md)|[.486P](../../assembler/masm/dot-486p.md)|[.586](../../assembler/masm/dot-586.md)|  
|[.586P](../../assembler/masm/dot-586p.md)|[.686](../../assembler/masm/dot-686.md)|[.686P](../../assembler/masm/dot-686p.md)|  
|[. K3D](../../assembler/masm/dot-k3d.md)|[.MMX](../../assembler/masm/dot-mmx.md)|[.XMM](../../assembler/masm/dot-xmm.md)|  
  
### Блоки повторяющееся задание  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[ДЛЯ](../../assembler/masm/for-masm.md)|[FORC](../Topic/FORC.md)|  
|[GOTO](../../assembler/masm/goto-masm.md)|[Повторение](../../assembler/masm/repeat.md)|[ПОКА](../../assembler/masm/while-masm.md)|  
  
### Область  
  
||||  
|-|-|-|  
|[COMM](../../assembler/masm/comm.md)|[EXTERN](../../assembler/masm/extern-masm.md)|[EXTERNDEF](../../assembler/masm/externdef.md)|  
|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[ОТКРЫТЫЙ](../Topic/PUBLIC%20\(MASM\).md)||  
  
### Сегмент  
  
||||  
|-|-|-|  
|[.ALPHA](../../assembler/masm/dot-alpha.md)|[TAKE](../../assembler/masm/assume.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|  
|[END](../../assembler/masm/end-masm.md)|[Элементы](../../assembler/masm/ends-masm.md)|[GROUP](../../assembler/masm/group.md)|  
|[Сегмент](../../assembler/masm/segment.md)|[.SEQ](../../assembler/masm/dot-seq.md)||  
  
### Упрощенный сегмент  
  
||||  
|-|-|-|  
|[.CODE](../../assembler/masm/dot-code.md)|[.CONST](../Topic/.CONST.md)|[.DATA](../../assembler/masm/dot-data.md)|  
|[.DATA?](../Topic/.DATA?.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|[.EXIT](../Topic/.EXIT.md)|  
|[.FARDATA](../../assembler/masm/dot-fardata.md)|[.FARDATA?](../../assembler/masm/dot-fardata-q.md)|[.MODEL](../../assembler/masm/dot-model.md)|  
|[.STACK](../Topic/.STACK.md)|[.STARTUP](../../assembler/masm/dot-startup.md)||  
  
### Строка.  
  
|||  
|-|-|  
|[CATSTR](../../assembler/masm/catstr.md)|[INSTR](../../assembler/masm/instr.md)|  
|[SIZESTR](../Topic/SIZESTR.md)|[SUBSTR](../Topic/SUBSTR.md)|  
  
### Структура и запись  
  
||||  
|-|-|-|  
|[Элементы](../../assembler/masm/ends-masm.md)|[ЗАПИСЬ](../../assembler/masm/record-masm.md)|[СТРУКТУРА](../Topic/STRUCT%20\(MASM\).md)|  
|[TYPEDEF](../../assembler/masm/typedef-masm.md)|[UNION](../../assembler/masm/union.md)||  
  
## См. также  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)
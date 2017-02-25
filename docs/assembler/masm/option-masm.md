---
title: "OPTION (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "option"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OPTION directive"
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# OPTION (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Включает и отключение функции ассемблера.  
  
## Синтаксис  
  
```  
  
OPTION   
optionlist  
  
```  
  
## Заметки  
 Доступные параметры:  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**ЭМУЛЯТОРА**|  
|**NOEMULATOR**|**ЭПИЛОГ**|**EXPR16**|**EXPR32**|  
|**ЯЗЫК**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**Смещение**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**Proc**|**ПРОЛОГ**|**READONLY**|**NOREADONLY**|  
|**ОБЛАСТИ**|**NOSCOPED**|**Сегмент**|SETIF2.|  
  
 Синтаксис ЯЗЫКА **ЯЗЫК ПАРАМЕТРА:**x, где x одно из c\#, SYSCALL, STDCALL, PASCAL, FORTRAN или Бейсика.  SYSCALL, PASCAL, FORTRAN и basic не поддерживаются с используется с .MODEL ПЛОСКИЙ.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)
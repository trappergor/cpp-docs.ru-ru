---
title: "ПАРАМЕТР (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d8e8049ecea3775b9df85eb1d5c8ee5e94a9243
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="option-masm"></a>OPTION (MASM)
Включает и отключает функции код на языке ассемблера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>Примечания  
 Доступны следующие параметры.  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**ЭМУЛЯТОР**|  
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|  
|**ЯЗЫК**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**PROLOGUE**|**ТОЛЬКО ДЛЯ ЧТЕНИЯ**|**NOREADONLY**|  
|**SCOPED**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 Синтаксис языка **параметр языка: *** x*, где *x* является одним из C, SYSCALL, STDCALL, языка PASCAL, FORTRAN или BASIC.  SYSCALL, языка PASCAL, FORTRAN и BASIC не поддерживает с [. МОДЕЛЬ](../../assembler/masm/dot-model.md) ПЛОСКОЙ.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)
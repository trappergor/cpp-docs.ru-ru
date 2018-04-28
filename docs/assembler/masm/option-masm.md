---
title: ПАРАМЕТР (MASM) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- option
dev_langs:
- C++
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80291c805cad3ef041fffc58983ff399da07c9d9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
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
|**NOEMULATOR**|**ЭПИЛОГА**|**EXPR16**|**EXPR32**|  
|**ЯЗЫК**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**СМЕЩЕНИЕ**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**ПРОЛОГ**|**ТОЛЬКО ДЛЯ ЧТЕНИЯ**|**NOREADONLY**|  
|**ОБЛАСТЬЮ ДЕЙСТВИЯ**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 Синтаксис языка **параметр языка: *** x*, где *x* является одним из C, SYSCALL, STDCALL, языка PASCAL, FORTRAN или BASIC.  SYSCALL, языка PASCAL, FORTRAN и BASIC не поддерживает с [. МОДЕЛЬ](../../assembler/masm/dot-model.md) ПЛОСКОЙ.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)
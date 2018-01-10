---
title: "ПАРАМЕТР (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: option
dev_langs: C++
helpviewer_keywords: OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f449606b143bfbf188e878b261f3d35017846862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
 Синтаксис языка **параметр языка:***x*, где *x* является одним из C, SYSCALL, STDCALL, языка PASCAL, FORTRAN или BASIC.  SYSCALL, языка PASCAL, FORTRAN и BASIC не поддерживает с [. МОДЕЛЬ](../../assembler/masm/dot-model.md) ПЛОСКОЙ.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)
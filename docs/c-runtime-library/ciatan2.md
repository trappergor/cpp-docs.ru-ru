---
title: "_Ciatan2 | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CIatan2
apilocation:
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- CIatan2
- _CIatan2
dev_langs:
- C++
helpviewer_keywords:
- _CIatan2 intrinsic
- CIatan2 intrinsic
ms.assetid: 31f8cc78-b79f-4576-b73b-8add18e08680
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a3163dcb844892cd4add63c4c985d3742831523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ciatan2"></a>_CIatan2
Вычисляет арктангенс *x* / *y*, где *x* и *y* представляют собой значения из верхней части стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __cdecl _CIatan2();  
```  
  
## <a name="remarks"></a>Примечания  
 Эта версия функции `atan2` включает специальные соглашения о вызовах, распознаваемые компилятором. Это ускоряет выполнение, поскольку исключает создание копий и помогает распределять регистры.  
  
 Полученное значение помещается в верхнюю часть стека.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** x86  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)
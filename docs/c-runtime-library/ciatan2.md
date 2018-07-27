---
title: _Ciatan2 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33abe3dd332bdb55decde308d67d0e1af13e13f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387149"
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
---
title: _CIlog10 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _CIlog10
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- CIlog10
- _CIlog10
dev_langs:
- C++
helpviewer_keywords:
- _CIlog10 intrinsic
- CIlog10 intrinsic
ms.assetid: 05d7fcaa-3cff-4cc5-8d44-015e7cacba24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 615a8818c6204298d06054ef77a1b95ab603b548
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386395"
---
# <a name="cilog10"></a>_CIlog10
Выполняет операцию `log10` с верхним значением в стеке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __cdecl _CIlog10();  
```  
  
## <a name="remarks"></a>Примечания  
 Эта версия функции `log10` включает специальные соглашения о вызовах, распознаваемые компилятором. Она ускоряет выполнение, так как исключает создание копий и помогает распределять регистры.  
  
 Полученное значение помещается в верхнюю часть стека.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** x86  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [log, logf, log10, log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)
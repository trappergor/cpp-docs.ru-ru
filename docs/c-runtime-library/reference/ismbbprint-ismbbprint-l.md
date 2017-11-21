---
title: "_ismbbprint, _ismbbprint_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbprint_l
- _ismbbprint
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbbprint_l
- _ismbbprint
- ismbbprint
- ismbbprint_l
dev_langs: C++
helpviewer_keywords:
- ismbbprint_l function
- ismbbprint function
- _ismbbprint function
- _ismbbprint_l function
ms.assetid: d08a061c-18a8-48f2-a75d-bff4870aec9d
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 451128fda38e5733cc9650e4783964d8c8aebfdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ismbbprint-ismbbprintl"></a>_ismbbprint, _ismbbprint_l
Определяет, является ли указанный многобайтовой символ печатным символом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _ismbbprint(  
   unsigned int c   
);  
int _ismbbprint_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Целое число, которое требуется проверить.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_ismbbprint` возвращает ненулевое значение, если выражение:  
  
```  
isprint || _ismbbkprint  
```  
  
 имеет ненулевое значение для `c`, или значение 0, если это не так. Функция`_ismbbprint` использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта. Функция`_ismbbprint_l` идентична за исключением того, что использует переданный языковой стандарт. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_ismbbprint`|\<mbctype.h>|  
|`_ismbbprint_l`|\<mbctype.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Классификация байтов](../../c-runtime-library/byte-classification.md)   
 [Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)
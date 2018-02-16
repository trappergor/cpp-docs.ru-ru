---
title: "_set_controlfp | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_controlfp
- _set_controlfp
dev_langs:
- C++
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b095fe13e8ecf20769ab833ace574d740fd185b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="setcontrolfp"></a>_set_controlfp
Задает управляющее слово блока операций с плавающей запятой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `newControl`  
 Значения битов в новом управляющем слове.  
  
 `mask`  
 Маска для установки битов нового управляющего слова.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Отсутствует.  
  
## <a name="remarks"></a>Примечания  
 Функция `_set_controlfp` аналогична функции `_control87`, но она задает только управляющее слово блока операций с плавающей запятой`newControl`. Биты в значениях показывают состояние элемента управления блоком операций с плавающей запятой. Состояние элемента управления блока операций с плавающей запятой разрешает программе изменять режимы точности, округления и бесконечности в пакете математических операций с числами с плавающей запятой. Можно также использовать функцию `_set_controlfp` для маскирования и демаскирования исключений, связанных с операциями с плавающей запятой. Дополнительные сведения см. в разделе [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  
  
 Эта функция устарела, при компиляции с параметром [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) Поскольку общеязыковая среда выполнения поддерживает только точность чисел с плавающей запятой по умолчанию.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Совместимость|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h>|только для процессоров x86|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)
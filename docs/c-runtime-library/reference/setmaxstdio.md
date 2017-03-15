---
title: "_setmaxstdio | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7947bb8de34b5e80321ddacf03e4606a53b5dc90
ms.lasthandoff: 02/24/2017

---
# <a name="setmaxstdio"></a>_setmaxstdio
Задает максимальное число одновременно открытых файлов на уровне `stdio`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `newmax`  
 Новое значение максимального числа одновременно открытых файлов на уровне `stdio`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение `newmax` в случае успешного выполнения, в противном случае возвращает значение –1.  
  
 Если `newmax` меньше значения `_IOB_ENTRIES` или превышает максимальное число дескрипторов, доступных в операционной системе, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает –1 и задает для `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_setmaxstdio` изменяет максимальное значение числа файлов, которые могут быть одновременно открыты на уровне `stdio`.  
  
 Ввод-вывод среды выполнения C теперь поддерживает большее число открытых файлов на базе платформ Win32, чем в предыдущих версиях. До 2048 файлов может быть открыто одновременно на уровне [lowio](../../c-runtime-library/low-level-i-o.md) (то есть, открыты и доступны для работы посредством функций `_open`, `_read`, `_write` и других, относящихся к семейству функций ввода и вывода). До 512 файлов может быть открыто одновременно на уровне [stdio](../../c-runtime-library/stream-i-o.md) (то есть, открыты и доступны для работы посредством функций `fopen`, `fgetc`, `fputc` и других, относящихся к семейству функций). Значение ограничения в 512 открытых файлов на уровне `stdio` можно увеличить до максимального значения 2048 с помощью функции `_setmaxstdio`.  
  
 Поскольку функции уровня `stdio`, например функция `fopen`, созданы на основе функций `lowio`, максимальное значение, равное 2048, является верхним пределом для числа одновременно открытых файлов, доступных в библиотеке среды выполнения C.  
  
> [!NOTE]
>  Это пороговое значение может превышать ограничения, поддерживаемые определенной конфигурацией и платформой Win32.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_setmaxstdio`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Пример использования `_setmaxstdio` см. в разделе [_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)

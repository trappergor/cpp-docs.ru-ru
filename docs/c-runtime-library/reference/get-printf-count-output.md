---
title: "_get_printf_count_output | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_printf_count_output
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
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
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
ms.openlocfilehash: 9f45a13d9911e82b2b624689fa6b9e5eb4b20d97
ms.lasthandoff: 02/24/2017

---
# <a name="getprintfcountoutput"></a>_get_printf_count_output
Указывает, поддерживает ли семейство функций [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) формат `%n`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _get_printf_count_output();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение указывает на наличие поддержки `%n`, а 0 — на отсутствие поддержки `%n`.  
  
## <a name="remarks"></a>Примечания  
 Если `%n` не поддерживается (по умолчанию), при обнаружении `%n` в строке формата любой из функций `printf` будет вызван обработчик недопустимого параметра, как описывается в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если поддержка `%n` включена (см. раздел [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)), поведение `%n` будет совпадать с описываемым в разделе [Символы поля типа printf](../../c-runtime-library/printf-type-field-characters.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).

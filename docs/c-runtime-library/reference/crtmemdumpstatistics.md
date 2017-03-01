---
title: "_CrtMemDumpStatistics | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemDumpStatistics
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
apitype: DLLExport
f1_keywords:
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 3d5065e62248a89de8dbe0ae38f354e0ead40ba6
ms.lasthandoff: 02/24/2017

---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics
Помещает в дамп данные заголовка отладки для указанного состояния кучи в понятной пользователю форме (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `state`  
 Указатель на состояние кучи для создания дампа.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtMemDumpStatistics` помещает в дамп данные заголовка отладки для указанного состояния кучи в понятной пользователю форме. Статистика дампа может использоваться приложением для отслеживания операций выделения памяти и выявления проблем с памятью. Состояние памяти может содержать состояние определенной кучи или разницу между двумя состояниями. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtMemDumpStatistics` удаляются на этапе предварительной обработки.  
  
 Функция `state` должен быть указателем на структуру `_CrtMemState`, которая заполняется функцией [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) или возвращается функцией [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) перед вызовом `_CrtMemDumpStatistics`. Если параметр `state` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, для `errno` задается значение `EINVAL` и никакие действия не выполняются. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Дополнительные сведения о функциях управления состоянием кучи и структуре `_CrtMemState` см. в разделе [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|-------------|---------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName>  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)

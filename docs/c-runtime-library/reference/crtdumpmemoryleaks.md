---
title: "_CrtDumpMemoryLeaks | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6a4a5c78b4301158d1f0d23f588d6afe353104a0
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks
Сбрасывает все блоки памяти в отладочной куче в случае утечки памяти (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
int _CrtDumpMemoryLeaks( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если утечка памяти обнаружена, `_CrtDumpMemoryLeaks` возвращает значение TRUE. В противном случае функция возвращает значение FALSE.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtDumpMemoryLeaks` определяет, произошла ли утечка памяти после начала выполнения программы. При обнаружении утечки данные заголовка отладки для всех объектов в куче записываются в форме, которую пользователь может прочитать. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtDumpMemoryLeaks` удаляются на этапе предварительной обработки.  
  
 Функция `_CrtDumpMemoryLeaks` часто вызывается в конце выполнения программы, чтобы проверить, освобождена ли вся выделенная приложением память. При прерывании работы программы эта функция может вызываться автоматически. Для этого необходимо включить битовое поле `_CRTDBG_LEAK_CHECK_DF` флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) с помощью функции [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md).  
  
 `_CrtDumpMemoryLeaks` вызывает [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) для получения текущего состояния кучи, а затем проверяет состояние блоков, которые не были освобождены. Обнаружив не освобожденный блок, `_CrtDumpMemoryLeaks` вызывает функцию [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) для записи сведений обо всех объектах, выделенных в куче с начала выполнения программы.  
  
 По умолчанию внутренние блоки среды выполнения C (`_CRT_BLOCK`) в операции с дампом памяти не включаются. Функцию [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) можно использовать для включения бита `_CRTDBG_CHECK_CRT_DF` флага `_crtDbgFlag` и включения этих блоков в процесс обнаружения утечек.  
  
 Дополнительные сведения о функциях управления состоянием кучи и структуре `_CrtMemState` см. в разделе [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 Пример использования `_CrtDumpMemoryLeaks` см. в описании [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)

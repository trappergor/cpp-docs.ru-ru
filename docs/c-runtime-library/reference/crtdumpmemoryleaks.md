---
title: "_CrtDumpMemoryLeaks | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 859f1918afc69054b13cab161f2d7b4801bcbd78
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
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
  
 Дополнительные сведения о функциях управления состоянием кучи и структуре `_CrtMemState` см. в статье [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtDumpMemoryLeaks`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 Пример использования `_CrtDumpMemoryLeaks` см. в описании [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)
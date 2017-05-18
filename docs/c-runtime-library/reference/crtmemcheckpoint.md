---
title: "_CrtMemCheckpoint | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
dev_langs:
- C++
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 1904bf5c2632b0913db8e5a9fb838a602615cb45
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint
Получает текущее состояние отладочной кучи и сохраняет его в предоставленной приложением структуре `_CrtMemState` (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `state`  
 Указатель на структуру `_CrtMemState` для заполнения контрольными точками памяти.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtMemCheckpoint` создает моментальный снимок текущего состояния отладочной кучи в любой данный момент. Этот моментальный снимок могут использовать другие функции управления состоянием кучи, такие как [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) , для обнаружения утечек памяти и других проблем. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы `_CrtMemState` удаляются на этапе предварительной обработки.  
  
 Приложение должно передать указатель в выделенный ранее экземпляр структуры `_CrtMemState` , определенный в файле Crtdbg.h в параметре `state` . Если при создании контрольной точки возникает ошибка `_CrtMemCheckpoint` , функция создает отчет об отладке `_CRT_WARN` , описывающий проблему.  
  
 Дополнительные сведения о функциях управления состоянием кучи и структуре `_CrtMemState` см. в статье [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
 Если параметр `state` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметру [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается значение `EINVAL`, а функция возвращает значение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h>, \<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** только отладочные версии UCRT.  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)

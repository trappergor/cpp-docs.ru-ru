---
title: "_CrtMemDumpAllObjectsSince | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
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
ms.openlocfilehash: 93904e03c38a74005682aabfc30c69b6f96b14c7
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince
Записывает в дамп сведения об объектах в куче с начала выполнения программы или перехода в указанное состояние кучи (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `state`  
 Указатель на состояние кучи, при наступлении которого должен начинаться дамп, или **NULL**.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtMemDumpAllObjectsSince` помещает в дамп данные заголовка отладки для выделенных в куче объектов в понятной пользователю форме. Данные дампа могут использоваться приложением для отслеживания операций выделения памяти и выявления проблем с памятью. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtMemDumpAllObjectsSince` удаляются на этапе предварительной обработки.  
  
 `_CrtMemDumpAllObjectsSince` использует значение параметра `state` для определения места, с которого должна начинаться операция дампа. Для того чтобы в указанном состоянии кучи запускался дамп, параметр `state` должен быть указателем на структуру **_CrtMemState**, заполненную функцией [_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) перед вызовом `_CrtMemDumpAllObjectsSince`. Если `state` имеет значение **NULL**, функция начинает запись дампа с началом выполнения программы.  
  
 Если приложение установило функцию-ловушку дампа, вызвав функцию [_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md), то каждый раз, когда `_CrtMemDumpAllObjectsSince` записывает в дамп информацию о типе блока `_CLIENT_BLOCK`, также вызывается функция дампа, предоставляемая приложением. По умолчанию внутренние блоки среды выполнения C (`_CRT_BLOCK`) в операции с дампом памяти не включаются. Функцию [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md) можно использовать для включения бита `_CRTDBG_CHECK_CRT_DF` флага **_crtDbgFlag** и включения этих блоков. Кроме того, блоки, помеченные как освобожденные или игнорируемые (**_FREE_BLOCK**, **_IGNORE_BLOCK**), в дамп памяти не включаются.  
  
 Дополнительные сведения о функциях управления состоянием кучи и структуре `_CrtMemState` см. в разделе [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 Пример использования функции `_CrtMemDumpAllObjectsSince` см. в разделе [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)

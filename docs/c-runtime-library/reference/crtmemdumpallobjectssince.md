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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1c04d21b1c4009bd93e608d1c243d5b459e2422
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
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
  
 Дополнительные сведения о функциях управления состоянием кучи и структуре `_CrtMemState` см. в разделе [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 Пример использования функции `_CrtMemDumpAllObjectsSince` см. в разделе [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы отладки](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)
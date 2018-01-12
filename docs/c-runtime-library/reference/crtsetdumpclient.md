---
title: "_CrtSetDumpClient | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs: C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf64ca280998ac25adbb380ff8245a0b8eecf797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient
Устанавливает определяемую приложением функцию для записи в дамп блоков памяти типа `_CLIENT_BLOCK` (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dumpClient`  
 Новая, определяемая клиентом функция дампа памяти, которую необходимо прикрепить к отладочному процессу дампа памяти среды выполнения C.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает определенную ранее функцию дампа клиентских блоков.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtSetDumpClient` позволяет приложению прикреплять собственную функцию для дампа объектов, хранящихся в блоках памяти `_CLIENT_BLOCK`, в процесс дампа памяти для отладки среды выполнения С. В результате каждый раз, когда функция дампа отладки, например [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) или [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md), записывает в дамп блок памяти `_CLIENT_BLOCK`, также вызывается функция дампа приложения. `_CrtSetDumpClient` предоставляет приложению простой способ для обнаружения утечек памяти и проверки содержимого данных, хранящихся в блоках `_CLIENT_BLOCK`, либо создания связанных с ними отчетов. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtSetDumpClient` удаляются на этапе предварительной обработки.  
  
 Функция `_CrtSetDumpClient` устанавливает новую определенную приложением функцию дампа, указанную в параметре `dumpClient`, и возвращает функцию дампа, определенную ранее. Пример функции дампа клиентского блока выглядит следующим образом:  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 Аргумент `userPortion` представляет собой указатель на начало части пользовательских данных в блоке памяти, а `blockSize` определяет объем выделяемого блока памяти в байтах. Функция дампа клиентского блока памяти должна возвращать значение `void`. Указатель на функцию, который передается `_CrtSetDumpClient`, имеет тип `_CRT_DUMP_CLIENT`, как определено в Crtdbg.h:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 Дополнительные сведения о функциях, работающих с блоками памяти типа `_CLIENT_BLOCK`, см. в разделе [Функции-ловушки клиентского блока](/visualstudio/debugger/client-block-hook-functions). Функцию [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md) можно использовать для получения сведений о типах и подтипов блоков.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)
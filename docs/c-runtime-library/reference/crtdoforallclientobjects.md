---
title: "_CrtDoForAllClientObjects | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs: C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dff8b99d6378928583cea0c5eec7d69130c56557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects
Вызывает функцию, предоставляемую приложением, для всех типов `_CLIENT_BLOCK` в куче (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _CrtDoForAllClientObjects(   
   void ( * pfn )( void *, void * ),  
   void *context  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pfn`  
 Указатель на функцию обратного вызова функции, предоставляемой приложением. Первый параметр для этой функции указывает на данные. Второй параметр является указателем контекста, передаваемым в вызов функции `_CrtDoForAllClientObjects`.  
  
 `context`  
 Указатель на контекст, предоставляемый приложением, для передачи в функцию, предоставляемую приложением.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtDoForAllClientObjects` выполняет поиск блоков памяти с типом `_CLIENT_BLOCK` в связанном списке кучи и вызывает функцию, предоставляемую приложением, если удается найти блок этого типа. Найденный блок и параметр `context` передаются как аргументы в функцию, предоставляемую приложением. Во время отладки приложение может отследить определенную группу выделений, явно вызывая функции отладочной кучи для выделения памяти и указывая, что блокам должен назначаться тип `_CLIENT_BLOCK` . Эти блоки затем могут отслеживаться по отдельности и включаться в разные отчеты об обнаружении утечки и состоянии памяти.  
  
 Если битовое поле `_CRTDBG_ALLOC_MEM_DF` флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) не включено, сразу возвращается `_CrtDoForAllClientObjects` . Если значение [_DEBUG](../../c-runtime-library/debug.md) не задано, вызовы `_CrtDoForAllClientObjects` удаляются во время предобработки.  
  
 Дополнительные сведения о типе `_CLIENT_BLOCK` и о том, как его могут использовать другие функции отладки, см. в статье [Types of blocks on the debug heap](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).  
  
 Если параметр `pfn` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметру [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается значение `EINVAL`, а функция возвращает значение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h>, \<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** отладочные версии только универсальных библиотек времени выполнения C.  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы отладки](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)
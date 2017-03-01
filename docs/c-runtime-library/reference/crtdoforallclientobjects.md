---
title: "_CrtDoForAllClientObjects | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtDoForAllClientObjects
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 316e062f4953874ce014f8288e86094209760faf
ms.lasthandoff: 02/24/2017

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
  
 Если битовое поле `_CRTDBG_ALLOC_MEM_DF` флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) не включено, сразу возвращается `_CrtDoForAllClientObjects`. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtDoForAllClientObjects` удаляются на этапе предварительной обработки.  
  
 Дополнительные сведения о типе `_CLIENT_BLOCK` и о том, как его могут использовать другие функции отладки, см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Если параметр `pfn` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметру [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается значение `EINVAL`, а функция возвращает значение.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtDoForAllClientObjects`|\<crtdbg.h>, \<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** отладочные версии только универсальных библиотек времени выполнения C.  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)   
 [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)

---
title: "_CrtCheckMemory | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
dev_langs:
- C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
caps.latest.revision: 12
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
ms.openlocfilehash: 82b64afbdd80e9b1433f8f9873b4e295fc2e20c1
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="crtcheckmemory"></a>_CrtCheckMemory
Проверяет целостность выделенных блоков памяти в отладочной куче (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
int _CrtCheckMemory( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения `_CrtCheckMemory` возвращает значение TRUE; в противном случае функция возвращает значение FALSE.  
  
## <a name="remarks"></a>Примечания  
 Функция `_CrtCheckMemory` проверяет память, выделенную диспетчеру отладочной кучи, проверяя основную кучу и каждый блок памяти. Если несогласованность памяти или ошибка возникают в базовой куче, сведениях о заголовке отладки или буферах перезаписи, `_CrtCheckMemory` создает отчет об отладке с информацией, описывающей условие возникновения ошибки. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtCheckMemory` удаляются на этапе предварительной обработки.  
  
 Поведением функции `_CrtCheckMemory` можно управлять, задав битовые поля флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) с помощью функции [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md). Если битовое поле **_CRTDBG_CHECK_ALWAYS_DF** включено, `_CrtCheckMemory` вызывается при каждом запросе операция выделения памяти. Несмотря на то, что этот метод замедляет выполнение, он позволяет быстро перехватывать ошибки. Если битовое поле **_CRTDBG_ALLOC_MEM_DF** отключено, `_CrtCheckMemory` не проверяет кучу, а сразу возвращает значение **TRUE**.  
  
 Так как эта функция возвращает значение **TRUE** или **FALSE**, ее можно передать в один из макросов [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Следующий пример вызывает сбой утверждения, если в куче обнаружено повреждение.  
  
```  
_ASSERTE( _CrtCheckMemory( ) );  
```  
  
 Дополнительные сведения о том, как использовать `_CrtCheckMemory` с другими функциями отладки, см. в разделе [Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Общие сведения об управлении памятью и отладочной куче см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtCheckMemory`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 Пример использования `_CrtCheckMemory` см. в описании [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)

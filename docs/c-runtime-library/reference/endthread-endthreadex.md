---
title: "_endthread, _endthreadex | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: 21
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
ms.openlocfilehash: e1e2211a34a7cc146d1ce3b791927ffc206edaef
ms.lasthandoff: 02/24/2017

---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex
Завершает поток; `_endthread` завершает поток, созданный `_beginthread` , а  `_endthreadex` завершает поток, созданный`_beginthreadex`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _endthread( void );  
void _endthreadex(   
   unsigned retval   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `retval`  
 Код выхода потока.  
  
## <a name="remarks"></a>Примечания  
 Можно явно вызвать `_endthread` или `_endthreadex` , чтобы завершить поток; однако `_endthread` или `_endthreadex` вызываются автоматически при возврате из подпрограммы потока, переданного в качестве параметра в `_beginthread` или `_beginthreadex`. Завершение потока вызовом функции `endthread` или `_endthreadex` помогает обеспечить правильное восстановление ресурсов, выделяемых для потока.  
  
> [!NOTE]
>  Для исполняемого файла, связанного с Libcmt.lib, не следует вызывать функцию [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API Win32. Это помешает системе времени выполнения освобождать выделенные ресурсы. `_endthread` и `_endthreadex` освобождают выделенные ресурсы потока и затем вызывают метод `ExitThread`.  
  
 `_endthread` автоматически закрывает дескриптор потока. (Это поведение отличается от API Win32 `ExitThread`.) Поэтому при использовании `_beginthread` и `_endthread` не следует явно закрывать дескриптор потока вызовом API Win32 [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx).  
  
 Аналогично функции `ExitThread` API Win32, функция `_endthreadex` не закрывает дескриптор потока. Поэтому при использовании `_beginthreadex` и `_endthreadex` необходимо закрыть дескриптор потока, вызвав API Win32 `CloseHandle`.  
  
> [!NOTE]
>  `_endthread` и `_endthreadex` блокируют вызов деструкторов C++, ожидающих в потоке.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_endthread`|\<process.h>|  
|`_endthreadex`|\<process.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Только многопоточные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
 См. пример для [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)

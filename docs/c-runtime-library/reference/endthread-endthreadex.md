---
title: "_endthread, _endthreadex | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
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
dev_langs: C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5abe2f0aa2f62048fefb2f79614e018fbdb51e08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex
Завершает поток; `_endthread` завершает поток, созданный `_beginthread` , а  `_endthreadex` завершает поток, созданный `_beginthreadex`.  
  
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
 Только многопоточные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md) .  
  
## <a name="example"></a>Пример  
 См. пример для [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)
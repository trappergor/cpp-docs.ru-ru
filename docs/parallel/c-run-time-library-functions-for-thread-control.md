---
title: "Функции библиотеки времени выполнения C для управления потоком | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- _endthread function
- threading [C++], controlling threads
- multithreading [C++], controlling threads
- _beginthreadex function
- _endthreadex function
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49d3d9029f85a8a80da6a7cd38bb26b887223d35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="c-run-time-library-functions-for-thread-control"></a>Функции управления потоками в библиотеке времени выполнения C
Все программы Win32 имеют по крайней мере один поток. Любой поток может создавать дополнительные потоки. Поток можно быстро завершить работу, а затем прерывает или оставаться активным в течение времени жизни программы.  
  
 Библиотеки времени выполнения LIBCMT и MSVCRT C предоставляются следующие функции для создания и завершения потоков: [_beginthread и _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) и [_endthread _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md).  
  
 `_beginthread` И `_beginthreadex` используются для создания нового потока и возвращают идентификатор потока в том случае, если операция выполнена успешно. Поток автоматически завершается при завершении выполнения или могла завершиться вызовом `_endthread` или `_endthreadex`.  
  
> [!NOTE]
>  Если планируется вызывать из приложения, созданного с помощью библиотеки Libcmt.lib подпрограммы времени выполнения C, необходимо запустить потоков с `_beginthread` или `_beginthreadex` функции. Не следует использовать функции Win32 `ExitThread` и `CreateThread`. С помощью `SuspendThread` может привести к взаимоблокировке, при блокировке ожидание поток для выполнения его права доступа к структуре данных времени выполнения C более одного потока.  
  
##  <a name="_core_the__beginthread_function"></a>Функции _beginthread и _beginthreadex  
 `_beginthread` И `_beginthreadex` функции создания нового потока. Поток обладает сегменты кода и данных процесса с другими потоками процесса, но имеет свои собственные уникальные значения регистров, место в стеке и текущий адрес инструкции. Система дает время ЦП для каждого потока, чтобы все потоки в процессе могут выполняться параллельно.  
  
 `_beginthread`и `_beginthreadex` похожи на [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) функции Win32 API, но имеет следующие различия:  
  
-   Они инициализируют определенные переменные библиотеки времени выполнения C. Это важно, только в том случае, если вы используете библиотеки времени выполнения C в потоках.  
  
-   `CreateThread`помогает обеспечивать Управление атрибутами безопасности. Эта функция используется для запуска потока в приостановленном состоянии.  
  
 `_beginthread`и `_beginthreadex` возвращается дескриптор для нового потока, в случае успеха или код ошибки, если произошла ошибка.  
  
##  <a name="_core_the__endthread_function"></a>Функции _endthread и _endthreadex  
 [_Endthread](../c-runtime-library/reference/endthread-endthreadex.md) функции завершения потока, созданного по `_beginthread` (и аналогично `_endthreadex` завершения потока, созданного по `_beginthreadex`). Потоки автоматически завершаются после их выполнения. `_endthread`и `_endthreadex` полезны для условного завершения потока. Поток, отвечающий соединением, например, может выйти из если его не удается получить контроль над COM-порт.  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)
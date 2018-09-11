---
title: Функции библиотеки времени выполнения C для управления потоками | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a0e57931b7f2af3f6232f140fd38155cfa5b2f8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195239"
---
# <a name="c-run-time-library-functions-for-thread-control"></a>Функции управления потоками в библиотеке времени выполнения C
Все программы Win32 имеют по крайней мере один поток. Любой поток может создавать дополнительные потоки. Поток может завершаться и остановите или оставаться активным в течение жизненного цикла программы.  
  
Библиотеки времени выполнения LIBCMT и MSVCRT C предоставляют следующие функции для создания и завершения потоков: [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) и [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md).  
  
`_beginthread` И `_beginthreadex` используются для создания нового потока и возвращает идентификатор потока, если операция выполнена успешно. Поток автоматически завершается при завершении выполнения или его можно завершить сам вызов `_endthread` или `_endthreadex`.  
  
> [!NOTE]
> Если вы собираетесь вызывать подпрограммы времени выполнения C из программы, созданные с помощью библиотеки Libcmt.lib, необходимо запустить потоков с `_beginthread` или `_beginthreadex` функции. Не следует использовать функции Win32 `ExitThread` и `CreateThread`. С помощью `SuspendThread` может привести к взаимоблокировке, при более чем один поток ожидает поток для завершения его доступ к структуре данных времени выполнения C.  
  
##  <a name="_core_the__beginthread_function"></a> Функции _beginthread и _beginthreadex  
 
`_beginthread` И `_beginthreadex` функции создают новый поток. Поток использует сегменты кода и данных процесса совместно с другими потоками данного процесса, но имеет свои собственные уникальные значения регистров, место в стеке и адрес текущей инструкции. Система дает время ЦП для каждого потока, чтобы все потоки в процессе могут выполняться одновременно.  
  
`_beginthread` и `_beginthreadex` аналогичны [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) функции интерфейса Win32 API, но имеет следующие различия:  
  
- Они инициализируют определенные переменные библиотеки времени выполнения C. Это важно, только в том случае, если вы используете библиотеки времени выполнения C в потоках.  
  
- `CreateThread` помогает обеспечивать контроль над атрибуты безопасности. Эта функция позволяет запустить поток в приостановленном состоянии.  
  
 `_beginthread` и `_beginthreadex` возвращает дескриптор нового потока, в случае успеха или код ошибки, если произошла ошибка.  
  
##  <a name="_core_the__endthread_function"></a> Функции _endthread и _endthreadex  
 
[_Endthread](../c-runtime-library/reference/endthread-endthreadex.md) потоке, созданном по завершении функции `_beginthread` (и аналогично `_endthreadex` завершает поток, созданный `_beginthreadex`). Потоки автоматически завершаются после их выполнения. `_endthread` и `_endthreadex` полезны для условного завершения потока. Поток, отвечающий соединением, например, может выйти из если он не может получить контроль над COM-порт.  
  
## <a name="see-also"></a>См. также  
 
[Реализация многопоточности на языке C с помощью функций Win32](multithreading-with-c-and-win32.md)
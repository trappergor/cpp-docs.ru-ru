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
ms.openlocfilehash: 2eaa1a0589cb001658b18144e06956eebd302287
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131858"
---
# <a name="c-run-time-library-functions-for-thread-control"></a>Функции управления потоками в библиотеке времени выполнения C
Все программы Win32 имеют по крайней мере один поток. Любой поток может создавать дополнительные потоки. Поток может завершаться и остановите или оставаться активным в течение жизненного цикла программы.  
  
Библиотеки времени выполнения LIBCMT и MSVCRT C предоставляют следующие функции для создания и завершения потоков: [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) и [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md).  
  
`_beginthread` И `_beginthreadex` используются для создания нового потока и возвращает идентификатор потока, если операция выполнена успешно. Поток автоматически завершается при завершении выполнения или его можно завершить сам вызов `_endthread` или `_endthreadex`.  
  
> [!NOTE]
> Если вы собираетесь вызывать подпрограммы времени выполнения C из программы, созданные с помощью библиотеки Libcmt.lib, необходимо запустить потоков с `_beginthread` или `_beginthreadex` функции. Не следует использовать функции Win32 `ExitThread` и `CreateThread`. С помощью `SuspendThread` может привести к взаимоблокировке, при более чем один поток ожидает поток для завершения его доступ к структуре данных времени выполнения C.  
  
##  <a name="_core_the__beginthread_function"></a> Функции _beginthread и _beginthreadex  
 
`_beginthread` И `_beginthreadex` функции создают новый поток. Поток использует сегменты кода и данных процесса совместно с другими потоками данного процесса, но имеет свои собственные уникальные значения регистров, место в стеке и адрес текущей инструкции. Система дает время ЦП для каждого потока, чтобы все потоки в процессе могут выполняться одновременно.  
  
`_beginthread` и `_beginthreadex` аналогичны [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) функции интерфейса Win32 API, но имеет следующие различия:  
  
- Они инициализируют определенные переменные библиотеки времени выполнения C. Это важно, только в том случае, если вы используете библиотеки времени выполнения C в потоках.  
  
- `CreateThread` помогает обеспечивать контроль над атрибуты безопасности. Эта функция позволяет запустить поток в приостановленном состоянии.  
  
 `_beginthread` и `_beginthreadex` возвращает дескриптор нового потока, в случае успеха или код ошибки, если произошла ошибка.  
  
##  <a name="_core_the__endthread_function"></a> Функции _endthread и _endthreadex  
 
[_Endthread](../c-runtime-library/reference/endthread-endthreadex.md) потоке, созданном по завершении функции `_beginthread` (и аналогично `_endthreadex` завершает поток, созданный `_beginthreadex`). Потоки автоматически завершаются после их выполнения. `_endthread` и `_endthreadex` полезны для условного завершения потока. Поток, отвечающий соединением, например, может выйти из если он не может получить контроль над COM-порт.  
  
## <a name="see-also"></a>См. также  
 
[Реализация многопоточности на языке C с помощью функций Win32](multithreading-with-c-and-win32.md)
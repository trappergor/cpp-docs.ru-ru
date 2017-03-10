---
title: "Управление процессами и средой | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d5198dcef7d24d2755c21b90802b19e809c5b8da
ms.lasthandoff: 02/24/2017

---
# <a name="process-and-environment-control"></a>Управление процессами и средой
С помощью подпрограмм для управления процессами можно запускать и останавливать процессы из программы, а также управлять ими, а с помощью подпрограмм для управления средой — получать и изменять сведения о среде операционной системы.  
  
### <a name="process-and-environment-control-functions"></a>Функции управления процессами и средой  
  
|Подпрограмма|Применение|Эквивалент .NET Framework|  
|-------------|---------|-------------------------------|  
|[abort](../c-runtime-library/reference/abort.md)|Прерывает процесс без очистки буферов или вызова функций, зарегистрированных с помощью `atexit` и `_onexit`|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Проверяет на наличие логических ошибок.|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|Макросы [_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Подобны `assert`, но доступны только в отладочных версиях библиотек времени выполнения|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|Подпрограммы расписания для выполнения при завершении программы.|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Создает новый поток в процессе операционной системы Windows.|[System::Threading::Thread::Start](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Выполняет процедуры завершения `exit` (например, очистка буферов), а затем возвращает управление вызывающей программе без прерывания процесса.|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|Выполняет процедуры завершения `_exit`, а затем возвращает управление вызывающей программе без прерывания процесса.|[System::Diagnostics::Process::CloseMainWindow](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[_cwait](../c-runtime-library/reference/cwait.md)|Ожидает завершения другого процесса.|[System::Diagnostics::Process::WaitForExit](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Завершает поток операционной системы Windows.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|Выполняет новый процесс со списком аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|Выполняет новый процесс со списком аргументов и заданной средой.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Выполняет новый процесс, используя переменную `PATH` и список аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Выполняет новый процесс, используя переменную `PATH`, заданную среду и список аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|Выполняет новый процесс с массивом аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|Выполняет новый процесс с массивом аргументов и заданной средой|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Выполняет новый процесс, используя переменную `PATH` и массив аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Выполняет новый процесс, используя переменную `PATH`, заданную среду и массив аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|Вызывает функции, зарегистрированные с помощью `atexit` и `_onexit`, очищает все буферы, закрывает все открытые файлы и завершает процесс.|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|Завершает процесс немедленно без вызова `atexit` или `_onexit` либо очистки буферов.|[System::Diagnostics::Process::Kill](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Получает значение переменной среды.|[System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[_getpid](../c-runtime-library/reference/getpid.md)|Получает идентификатор процесса.|[System::Diagnostics::Process::Id](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Восстанавливает сохраненную среду стека и использует ее для выполнения нелокальной команды `goto`.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Подпрограммы расписания, которые следует выполнять при завершении программы. Используются для обеспечения совместимости с Microsoft C/C++ версии 7.0 и более ранними версиями.|[System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[_pclose](../c-runtime-library/reference/pclose.md)|Ожидает новый обработчик команд и закрывает поток по связанному каналу.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|Сообщение об ошибке печати.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_pipe](../c-runtime-library/reference/pipe.md)|Создает канал для чтения и записи.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|Создает канал и выполняет команду.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Получает или изменяет значения переменной среды.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[raise](../c-runtime-library/reference/raise.md)|Отправляет сигнал для вызывающего процесса.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Сохраняет среду стека. Используется для выполнения нелокальной команды `goto`.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[signal](../c-runtime-library/reference/signal.md)|Обрабатывает сигнал прерывания.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Создает процесс и выполняет его с указанным списком аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Создает процесс и выполняет его с указанным списком аргументов и средой.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Создает процесс и выполняет его, используя переменную `PATH` и указанный список аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Создает процесс и выполняет его, используя переменную `PATH`, указанную среду и список аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Создает процесс и выполняет его с указанным массивом аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Создает процесс и выполняет его с указанной средой и массивом аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Создает процесс и выполняет его, используя переменную `PATH` и указанный массив аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Создает процесс и выполняет его, используя переменную `PATH`, указанную среду и массив аргументов.|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|Выполняет команду операционной системы.|[System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 В операционной системе Windows порожденный процесс эквивалентен процессу создания. Любой процесс может использовать функцию `_cwait` для ожидания любого другого процесса с известным идентификатором.  
  
 Разница между семействами `_exec` и `_spawn` заключается в том, что функция `_spawn` может переключить управление из нового процесса к вызывающему. В функции `_spawn` вызывающий и новый процесс находятся в памяти, если не указано `_P_OVERLAY`. В функции `_exec` новый процесс накладывается на вызывающий, поэтому управление не может вернуться к вызывающему процессу, если при попытке запуска выполнения нового процесса не произойдет ошибка.  
  
 Функции в семействе `_exec` и `_spawn` отличаются методом поиска файла, который выполняется как новый процесс, формой, в которой аргументы передаются в новый процесс, и способом настройки среды, как показано в следующей таблице. Используйте функцию, передающую список аргументов, когда число аргументов является постоянным или известно в момент компиляции. Используйте функцию, передающую указатель в массив, содержащий аргументы, когда число аргументов определяется во время выполнения. Сведения в следующей таблице также применимы к аналогам функции `_spawn` и `_exec` с расширенными символами.  
  
### <a name="spawn-and-exec-function-families"></a>Функции семейств _spawn и _exec  
  
|Функции|Использование переменной PATH для поиска файла|Соглашение о передаче аргументов|Параметры среды|  
|---------------|--------------------------------------|----------------------------------|--------------------------|  
|`_execl, _spawnl`|Нет|Список|Унаследовано от вызывающего процесса|  
|`_execle, _spawnle`|Нет|Список|Указатель на таблицу среды для нового процесса, переданного в качестве последнего аргумента|  
|`_execlp, _spawnlp`|Да|Список|Унаследовано от вызывающего процесса|  
|`_execlpe, _spawnlpe`|Да|Список|Указатель на таблицу среды для нового процесса, переданного в качестве последнего аргумента|  
|`_execv, _spawnv`|Нет|Массив|Унаследовано от вызывающего процесса|  
|`_execve, _spawnve`|Нет|Массив|Указатель на таблицу среды для нового процесса, переданного в качестве последнего аргумента|  
|`_execvp, _spawnvp`|Да|Массив|Унаследовано от вызывающего процесса|  
|`_execvpe, _spawnvpe`|Да|Массив|Указатель на таблицу среды для нового процесса, переданного в качестве последнего аргумента|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)

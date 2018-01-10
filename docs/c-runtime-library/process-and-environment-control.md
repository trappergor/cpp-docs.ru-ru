---
title: "Управление процессами и средой | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.programs
dev_langs: C++
helpviewer_keywords:
- processes, stopping
- processes, administrative tasks
- parent process
- processes, starting
- environment control routines
- process control routines
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cee24f0e5142af37681bd293a3be3600ddbd1cc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="process-and-environment-control"></a>Управление процессами и средой
С помощью подпрограмм для управления процессами можно запускать и останавливать процессы из программы, а также управлять ими, а с помощью подпрограмм для управления средой — получать и изменять сведения о среде операционной системы.  
  
### <a name="process-and-environment-control-functions"></a>Функции управления процессами и средой  
  
|Подпрограмма|Использовать|  
|-------------|---------|  
|[abort](../c-runtime-library/reference/abort.md)|Прерывает процесс без очистки буферов или вызова функций, зарегистрированных с помощью `atexit` и `_onexit`|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Проверяет на наличие логических ошибок.|  
|Макросы [_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Подобны `assert`, но доступны только в отладочных версиях библиотек времени выполнения|  
|[atexit](../c-runtime-library/reference/atexit.md)|Подпрограммы расписания для выполнения при завершении программы.|  
|[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)|Создает новый поток в процессе операционной системы Windows.|  
|[_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Выполняет процедуры завершения `exit` (например, очистка буферов), а затем возвращает управление вызывающей программе без прерывания процесса.|  
|[_c_exit](../c-runtime-library/reference/cexit-c-exit.md)|Выполняет процедуры завершения `_exit`, а затем возвращает управление вызывающей программе без прерывания процесса.|  
|[_cwait](../c-runtime-library/reference/cwait.md)|Ожидает завершения другого процесса.|  
|[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)|Завершает поток операционной системы Windows.|  
|[_execl, _wexecl](../c-runtime-library/reference/execl-wexecl.md)|Выполняет новый процесс со списком аргументов.|  
|[_execle, _wexecle](../c-runtime-library/reference/execle-wexecle.md)|Выполняет новый процесс со списком аргументов и заданной средой.|  
|[_execlp, _wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Выполняет новый процесс, используя переменную `PATH` и список аргументов.|  
|[_execlpe, _wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Выполняет новый процесс, используя переменную `PATH`, заданную среду и список аргументов|  
|[_execv, _wexecv](../c-runtime-library/reference/execv-wexecv.md)|Выполняет новый процесс с массивом аргументов|  
|[_execve, _wexecve](../c-runtime-library/reference/execve-wexecve.md)|Выполняет новый процесс с массивом аргументов и заданной средой|  
|[_execvp, _wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Выполняет новый процесс, используя переменную `PATH` и массив аргументов.|  
|[_execvpe, _wexecvpe](../c-runtime-library/reference/execvpe-wexecvpe.md)|Выполняет новый процесс, используя переменную `PATH`, заданную среду и массив аргументов.|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|Вызывает функции, зарегистрированные с помощью `atexit` и `_onexit`, очищает все буферы, закрывает все открытые файлы и завершает процесс.|  
|[_exit](../c-runtime-library/reference/exit-exit-exit.md)|Завершает процесс немедленно без вызова `atexit` или `_onexit` либо очистки буферов.|  
|[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Получает значение переменной среды.|  
|[_getpid](../c-runtime-library/reference/getpid.md)|Получает идентификатор процесса.|[System::Diagnostics::Process::Id](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Восстанавливает сохраненную среду стека и использует ее для выполнения нелокальной команды `goto`.|  
|[_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Подпрограммы расписания, которые следует выполнять при завершении программы. Используются для обеспечения совместимости с Microsoft C/C++ версии 7.0 и более ранними версиями.|  
|[_pclose](../c-runtime-library/reference/pclose.md)|Ожидает новый обработчик команд и закрывает поток по связанному каналу.|  
|[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)|Сообщение об ошибке печати.|  
|[_pipe](../c-runtime-library/reference/pipe.md)|Создает канал для чтения и записи.|  
|[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)|Создает канал и выполняет команду.|  
|[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md), [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Получает или изменяет значения переменной среды.|  
|[raise](../c-runtime-library/reference/raise.md)|Отправляет сигнал для вызывающего процесса.|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Сохраняет среду стека. Используется для выполнения нелокальной команды `goto`.|  
|[signal](../c-runtime-library/reference/signal.md)|Обрабатывает сигнал прерывания.|  
|[_spawnl, _wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|Создает процесс и выполняет его с указанным списком аргументов.|  
|[_spawnle, _wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Создает процесс и выполняет его с указанным списком аргументов и средой.|  
|[_spawnlp, _wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Создает процесс и выполняет его, используя переменную `PATH` и указанный список аргументов.|  
|[_spawnlpe, _wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|Создает процесс и выполняет его, используя переменную `PATH`, указанную среду и список аргументов.|  
|[_spawnv, _wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Создает процесс и выполняет его с указанным массивом аргументов.|  
|[_spawnve, _wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Создает процесс и выполняет его с указанной средой и массивом аргументов.|  
|[_spawnvp, _wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Создает процесс и выполняет его, используя переменную `PATH` и указанный массив аргументов.|  
|[_spawnvpe, _wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|Создает процесс и выполняет его, используя переменную `PATH`, указанную среду и массив аргументов.|  
|[system, _wsystem](../c-runtime-library/reference/system-wsystem.md)|Выполняет команду операционной системы.|  
  
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
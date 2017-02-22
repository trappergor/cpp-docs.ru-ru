---
title: "Управление процессами и средой | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "процедуры управления средой"
  - "родительский процесс"
  - "процедуры управления процессами"
  - "процессы, задачи администрирования"
  - "процессы, запуск"
  - "процессы, остановка"
ms.assetid: 7fde74c3-c2a6-4d15-84b8-092160d60c3e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Управление процессами и средой
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используйте процедуры управления процессами для запуска, остановки и управления процессами из программы.  Используйте процедуры управления средой выполнения, чтобы получать и изменять сведения о среде операционной системы.  
  
### Функции управления процессами и средой  
  
|Подпрограмма|Применение|Эквивалент в .NET Framework|  
|------------------|----------------|---------------------------------|  
|[abort](../c-runtime-library/reference/abort.md)|Прерывает процесс без сбрасывания буферов или вызова функций, зарегистрированных `atexit` и `_onexit`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md)|Тест на логическую ошибку|[\<caps:sentence id\="tgt14" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|Макросы [\_ASSERT, \_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)|Аналогичны `assert`, но доступны только в версиях отладки библиотек времени выполнения|[\<caps:sentence id\="tgt17" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[atexit](../c-runtime-library/reference/atexit.md)|Поставить в очередь процедуры для выполнения при завершении работы программы|[\<caps:sentence id\="tgt20" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_beginthread, \_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md)|Создают новый поток в процессе операционной системы Windows|[\<caps:sentence id\="tgt23" sentenceid\="221e38ecc6535bce91af4e1a19f464d1" class\="tgtSentence"\>System::Threading::Thread::Start\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)|  
|[\_cexit](../c-runtime-library/reference/cexit-c-exit.md)|Выполняет процедуры завершения `exit` \(например, сброс буферов\), а затем возвращает управление вызывающей программе без завершения процесса|[\<caps:sentence id\="tgt26" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_c\_exit](../c-runtime-library/reference/cexit-c-exit.md)|Выполняет процедуры завершения `_exit`, а затем возвращает управление вызывающей программе без завершения процесса|[\<caps:sentence id\="tgt29" sentenceid\="46302f19d05c09c5875a795cb64800f9" class\="tgtSentence"\>System::Diagnostics::Process::CloseMainWindow\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)|  
|[\_cwait](../c-runtime-library/reference/cwait.md)|Ожидает завершение другого процесса|[\<caps:sentence id\="tgt32" sentenceid\="d9c88c429eaacaa9f37d91d29bc6504e" class\="tgtSentence"\>System::Diagnostics::Process::WaitForExit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.waitforexit.aspx)|  
|[\_endthread, \_endthreadex](../Topic/_endthread,%20_endthreadex.md)|Завершают поток операционной системы Windows|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_execl, \_wexecl](../Topic/_execl,%20_wexecl.md)|Выполнят новый процесс со списком аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execle, \_wexecle](../c-runtime-library/reference/execle-wexecle.md)|Выполняют новый процесс со списком аргументов и указанной средой|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlp, \_wexeclp](../c-runtime-library/reference/execlp-wexeclp.md)|Выполняют новый процесс с использованием переменной `PATH` и списка аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execlpe, \_wexeclpe](../c-runtime-library/reference/execlpe-wexeclpe.md)|Выполняют новый процесс с использованием переменной `PATH`, указанной среды и списка аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execv, \_wexecv](../c-runtime-library/reference/execv-wexecv.md)|Выполнят новый процесс с массивом аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execve, \_wexecve](../c-runtime-library/reference/execve-wexecve.md)|Выполняют новый процесс с массивом аргументов и указанной средой|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvp, \_wexecvp](../c-runtime-library/reference/execvp-wexecvp.md)|Выполняют новый процесс с использованием переменной `PATH` и массива аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_execvpe, \_wexecvpe](../Topic/_execvpe,%20_wexecvpe.md)|Выполняют новый процесс с использованием переменной `PATH`, указанной среды и массива аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[exit](../c-runtime-library/reference/exit-exit-exit.md)|Вызывает функции, зарегистрированные `atexit` и `_onexit`, сбрасывает все буферы, закрывает все открытые файлы и завершает процесс|[\<caps:sentence id\="tgt64" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[\_exit](../c-runtime-library/reference/exit-exit-exit.md)|Завершает процесс немедленно без вызова `atexit` или `_onexit` или сбрасывания буферов|[\<caps:sentence id\="tgt67" sentenceid\="811a70e90f150f212690505b37a46c0f" class\="tgtSentence"\>System::Diagnostics::Process::Kill\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.kill.aspx)|  
|[getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md), [getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Получение значения переменной среды|[\<caps:sentence id\="tgt70" sentenceid\="795988b9277d74ea3b722ecd42dcb29d" class\="tgtSentence"\>System::Environment::GetEnvironmentVariable\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)|  
|[\_getpid](../Topic/_getpid.md)|Получает идентификатор процесса|[\<caps:sentence id\="tgt73" sentenceid\="745b82c461dc74b15540e9622f7cd7bd" class\="tgtSentence"\>System::Diagnostics::Process::Id\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.id.aspx)|  
|[longjmp](../c-runtime-library/reference/longjmp.md)|Восстанавливает сохраненную среду стека; используйте для выполнения дальнего `goto`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_onexit](../c-runtime-library/reference/onexit-onexit-m.md)|Планирует процедуры для выполнения при завершении работы программы; используйте для совместимости с версией Microsoft C\/C\+\+ 7.0 и более ранними|[\<caps:sentence id\="tgt81" sentenceid\="db022fa9aa2a12937c3610e3eb32e80f" class\="tgtSentence"\>System::Diagnostics::Process::Exited\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)|  
|[\_pclose](../Topic/_pclose.md)|Ожидает новый обработчик команд и закрывает поток связанного канала|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[perror, \_wperror](../c-runtime-library/reference/perror-wperror.md)|Печатают сообщение об ошибке.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_pipe](../c-runtime-library/reference/pipe.md)|Создает канал для чтения и записи.|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md)|Создают канал и выполняют команду|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md), [\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Добавляют или изменяют значение переменной среды|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[raise](../c-runtime-library/reference/raise.md)|Отправляет сигнал вызывающему процессу|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[setjmp](../c-runtime-library/reference/setjmp.md)|Сохраняет среду стека; используйте для выполнения дальнего `goto`|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[signal](../c-runtime-library/reference/signal.md)|Обрабатывает сигнал прерывания|Неприменимо.  Для вызова стандартной функции C используйте `PInvoke`.  Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_spawnl, \_wspawnl](../Topic/_spawnl,%20_wspawnl.md)|Создают и выполняют новый процесса с указанным списком аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnle, \_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|Создают и выполняют новый процесс с указанным списком аргументов и средой|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlp, \_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|Создают и выполняют новый процесс с использованием переменной `PATH` и указанного списка аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnlpe, \_wspawnlpe](../Topic/_spawnlpe,%20_wspawnlpe.md)|Создают и выполняют новый процесс с использованием переменной `PATH`, указанной среды и указанного списка аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnv, \_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|Создают и выполняют новый процесса с указанным массивом аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnve, \_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|Создают и выполняют новый процесс с указанным массивом аргументов и средой|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvp, \_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|Создают и выполняют новый процесс с использованием переменной `PATH` и указанного массива аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[\_spawnvpe, \_wspawnvpe](../Topic/_spawnvpe,%20_wspawnvpe.md)|Создают и выполняют новый процесс с использованием переменной `PATH`, указанной среды и указанного массива аргументов|[System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx), [System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx)|  
|[system, \_wsystem](../c-runtime-library/reference/system-wsystem.md)|Выполняют команду операционной системы|[System::Diagnostics::ProcessStartInfo Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.processstartinfo.aspx), [System::Diagnostics::Process Class](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.aspx)|  
  
 В операционной системе Windows порожденный процесс эквивалентен порождающему процессу.  Любой процесс может использовать `_cwait` для ожидания любого другого процесса с известным идентификатором.  
  
 Различие между семействами `_exec` и `_spawn` в том, что функции `_spawn` могут возвращать управления из нового процесса вызывающему процессу.  В функции `_spawn` и вызывающий, и новый процесс содержатся в памяти, если `_P_OVERLAY` не указана.  В функции `_exec`, новый процесс перекрывает вызывающий процесс, поэтому управление не может возвратиться вызывающему процессу, если не возникают ошибки при попытке запуска нового процесса.  
  
 Различия между функциями семейства `_exec`, как и между функциями семейства `_spawn`, включают в себя метод поиска файла для выполнения в новом процессе, вид, в котором аргументы передаются в новый процесс и метод установки среды, как показано в следующей таблице.  Используйте функцию, которая передает список аргументов, когда число аргументов постоянно или известно во время компиляции.  Используйте функцию, которая передает указатель на массив, содержащий аргументы, когда число аргументов определяется во время выполнения.  Сведения в таблице также применимы к аналогам функций `_spawn` и `_exec` для расширенных символов.  
  
### функции семейства \_spawn и \_exec  
  
|Функции|Используют переменную PATH, чтобы найти файл|Соглашение о передаче аргументов|Параметры среды|  
|-------------|--------------------------------------------------|--------------------------------------|---------------------|  
|`_execl, _spawnl`|Нет|List|Наследуются у вызывающего процесса|  
|`_execle, _spawnle`|Нет|List|Указатель на таблицу среды для нового процесса передается как последний аргумент|  
|`_execlp, _spawnlp`|Да|List|Наследуются у вызывающего процесса|  
|`_execlpe, _spawnlpe`|Да|List|Указатель на таблицу среды для нового процесса передается как последний аргумент|  
|`_execv, _spawnv`|Нет|Массив|Наследуются у вызывающего процесса|  
|`_execve, _spawnve`|Нет|Массив|Указатель на таблицу среды для нового процесса передается как последний аргумент|  
|`_execvp, _spawnvp`|Да|Массив|Наследуются у вызывающего процесса|  
|`_execvpe, _spawnvpe`|Да|Массив|Указатель на таблицу среды для нового процесса передается как последний аргумент|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
---
title: "abort | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "abort"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abort - функция"
  - "прерывание текущего процесса"
  - "процессы, прерывание"
ms.assetid: a797783b-40ed-4bdb-a2cd-14ffede39e8a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# abort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Прерывает текущий процесс и возвращает код ошибки.  
  
> [!NOTE]
>  Не используйте этот метод для завершения приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], за исключением сценариев тестирования или отладки.  Закрытие приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] программным способом или с помощью пользовательского интерфейса на допускается в соответствии с разделом 3.6 [сертификационных требований к приложениям для Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889).  Дополнительные сведения см. в разделе [Жизненный цикл приложения \(приложения Магазина Windows\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Синтаксис  
  
```  
void abort( void );  
```  
  
## Возвращаемое значение  
 `abort` не возвращает управление вызывающему процессу.  По умолчанию он выполняет проверку на наличие обработчика сигналов прерывания и создает `SIGABRT`, если он задано.  Затем функция `abort` используется для завершения текущего процесса и возвращает код завершения в процесс.  
  
## Заметки  
 **Блок, относящийся только к системам Майкрософт**  
  
 По умолчанию при сборке приложения с отладочной библиотекой времени выполнения процедура `abort` выводит сообщение об ошибке, прежде чем создается `SIGABRT`.  Для консольных приложений, работающих в режиме консоли консоли, сообщение отправляется в `STDERR`.  Классические приложения Windows и консольные приложения, работающих в оконном режиме, выводят сообщения в окне сообщения.  Чтобы отключить сообщение, используйте функцию [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md), чтобы снять флажок `_WRITE_ABORT_MSG`.  Сообщение, отображаемое зависит от используемой версии среды выполнения.  Для приложений, построенных с использованием последних версий Visual C\+\+, сообщение имеет следующий вид:  
  
 `R6010`  
  
 `- abort() has been called`  
  
 В предыдущих версиях библиотеки времени выполнения C выводилось следующее сообщение:  
  
 "`This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information.`"  
  
 Если программа скомпилирована в режиме отладки, в окне сообщений отображаются варианты **Прервать**, **Повторить** и **Пропустить**.  Если пользователь выбирает **Прервать**, программа завершается немедленно и возвращает код завершения 3.  Если пользователь выбирает **Повторить**, вызывается отладчик для JIT\-отладки, если это возможно.  Если пользователь выбирает **Пропустить**, то `abort` продолжает нормальную обработку.  
  
 И в окончательных, и в отладочных сборках `abort` затем проверяет, установлен ли обработчик сигналов прерывания.  Если задан обработчик сигналов, отличный от используемого по умолчанию, `abort` вызывает метод `raise(SIGABRT)`.  Используйте функцию [signal](../../c-runtime-library/reference/signal.md), чтобы связать функцию обработчика сигнала прерывания с сигналом `SIGABRT`.  Можно выполнять пользовательский действие — например, очищать ресурсы или заносить информацию в журнал, — и завершать приложение с пользовательским кодом ошибки в функции обработчика.  Если пользовательский обработчик сигналов не определен, `abort` не создает сигнал `SIGABRT`.  
  
 По умолчанию в неотладочных сборках классических или консольных приложений `abort` затем вызывает механизм отчетов об ошибках Windows \(Dr.  Watson\) для сообщения о сбоях в Microsoft.  Это расширение функциональности может включить или запрещено путем вызова метода `_set_abort_behavior` и устанавливать или маскировать флажок `_CALL_REPORTFAULT`.  Когда этот флаг установлен, Windows отображает окно сообщения, содержащее текст наподобие следующего: "Возникшая проблема привела к прекращению работы программы.". Пользователь может вызвать отладчик с помощью кнопки **Отладка** или нажав кнопку **Закрыть программу**, чтобы завершить приложение с кодом ошибки, определенной ОС.  
  
 Если обработчик отчетов об ошибках Windows не вызван, метод `abort` вызывает метод [\_exit](../../c-runtime-library/reference/exit-exit-exit.md), чтобы завершить процесс с кодом завершения 3 и возвращает управление родительскому процессу или операционной системе.  `_exit` не очищает буферы потока или не выполняет обработку `atexit`\/`_onexit`.  
  
 Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](../Topic/CRT%20Debugging%20Techniques.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`abort`|\<process.h\> или \<stdlib.h\>|  
  
## Пример  
 Следующая программа пытается открыть файл и прерывается, если эта попытка завершается ошибкой.  
  
```c  
// crt_abort.c  
// compile with: /TC  
// This program demonstrates the use of  
// the abort function by attempting to open a file  
// and aborts if the attempt fails.  
  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    FILE    *stream = NULL;  
    errno_t err = 0;  
  
    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );  
    if ((err != 0) || (stream == NULL))  
    {  
        perror( "File could not be opened" );  
        abort();  
    }  
    else  
    {  
        fclose( stream );  
    }  
}  
```  
  
  **Не удалось открыть файл: нет такого файла или каталога**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Использование функции abort](../../cpp/using-abort.md)   
 [Функция abort](../../c-language/abort-function-c.md)   
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции \_exec, \_wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [\_DEBUG](../Topic/_DEBUG.md)   
 [\_set\_abort\_behavior](../../c-runtime-library/reference/set-abort-behavior.md)
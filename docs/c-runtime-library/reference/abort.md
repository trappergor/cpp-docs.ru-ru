---
title: "abort | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- abort
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
- Abort
dev_langs:
- C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
ms.assetid: a797783b-40ed-4bdb-a2cd-14ffede39e8a
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 98633c2575d7447292562e024dc2c5e9e3207d06
ms.lasthandoff: 02/24/2017

---
# <a name="abort"></a>abort
Прерывает текущий процесс и возвращает код ошибки.  
  
> [!NOTE]
>  Не используйте этот метод для завершения приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], за исключением сценариев тестирования или отладки. Закрытие приложения [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] программным способом или с помощью пользовательского интерфейса не допускается в соответствии с [сертификационными требованиями к приложениям для Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889). Дополнительные сведения см. в разделе [Жизненный цикл приложений (приложения для Магазина Windows)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void abort( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `abort` не возвращает управление вызывающему процессу. По умолчанию он проверяет наличие обработчика прерывания сигнала и вызывает `SIGABRT`, если он задан. Затем `abort` завершает текущий процесс и возвращает код выхода для родительского процесса.  
  
## <a name="remarks"></a>Примечания  
 **Блок, относящийся только к системам Майкрософт**  
  
 По умолчанию при сборке приложения с использованием отладочной библиотеки среды выполнения подпрограмма `abort` выдает сообщение об ошибке, прежде чем появляется `SIGABRT`. Для консольных приложений, работающих в режиме консоли, отправляется сообщение в `STDERR`. Классические приложения Windows и консольные приложения, запускаемые в окнах, отображают сообщение в окне сообщений. Чтобы отключить сообщение, снимите флаг `_WRITE_ABORT_MSG` с помощью функции [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md). Отображаемое сообщение зависит от версии используемой среды выполнения. Для приложений, собранных с использованием последней версии Visual C++ сообщение выглядит следующим образом:  
  
 `R6010`  
  
 `- abort() has been called`  
  
 В предыдущих версиях библиотеки среды выполнения C отображается следующее сообщение:  
  
 "`This application has requested the Runtime to terminate it in an unusual way. Please contact the application's support team for more information.`"  
  
 При компиляции программы в режиме отладки в окне сообщения отображаются параметры **Прервать**, **Повторить** или **Пропустить**. Если пользователь выбирает параметр **Прервать**, программа немедленно завершается и возвращает код выхода 3. Если пользователь выбирает параметр **Повторить**, вызывается отладчик (если он доступен) для JIT-отладки. Если пользователь выбирает параметр **Пропустить**, `abort` продолжает работу в обычном режиме.  
  
 Затем и в окончательной, и в отладочной сборке `abort` проверяет, задает ли обработчик прерывания сигнала. Если задан обработчик сигнала, не используемый по умолчанию, `abort` вызывает `raise(SIGABRT)`. С помощью функции [signal](../../c-runtime-library/reference/signal.md) свяжите функцию обработчика сигналов прерывания с сигналом `SIGABRT`. Вы можете выполнить пользовательские действия — например, освободить ресурсы или записать данные сведений — и завершить работу приложения с кодом ошибки в функции обработчика. Если пользовательский обработчик сигналов не определен, `abort` не вызывает сигнал `SIGABRT`.  
  
 По умолчанию в сборках классических и консольных приложений, не предназначенных для отладки, после этого `abort` вызывает механизм Windows (Dr. Watson), передающий корпорации Майкрософт отчеты о сбоях. Это поведение можно включить или отключить, вызвав `_set_abort_behavior` и задав или замаскировав флаг `_CALL_REPORTFAULT`. Если флаг установлен, в Windows появится окно сообщения, содержащее текст вида "Возникшая проблема привела к прекращению работы программы". Пользователь может вызвать отладчик с помощью кнопки **Отладка** или нажать кнопку **Закрыть программу**, чтобы завершить приложение с кодом ошибки, который определяется операционной системой.  
  
 Если обработчик отчетов об ошибках Windows не вызывается, `abort` вызывает функцию [_exit](../../c-runtime-library/reference/exit-exit-exit.md), чтобы завершить процесс с кодом выхода 3, а затем возвращает управление родительскому процессу или операционной системе. `_exit` не очищает буферы потоков и не выполняет обработку `atexit`/`_onexit`.  
  
 Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`abort`|\<process.h> или \<stdlib.h>|  
  
## <a name="example"></a>Пример  
 Следующая программа пытается открыть файл и прерывается, если попытка завершается неудачей.  
  
```C  
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
  
```Output  
File could not be opened: No such file or directory  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Использование функции abort](../../cpp/using-abort.md)   
 [Функция abort](../../c-language/abort-function-c.md)   
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)   
 [_DEBUG](../../c-runtime-library/debug.md)   
 [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)

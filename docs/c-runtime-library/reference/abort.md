---
title: "abort | Документация Майкрософт"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: abort
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
f1_keywords: Abort
dev_langs: C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6577ca7927d42e12aa62ed100b9572b7270208f
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="abort"></a>abort

Прерывает текущий процесс и возвращает код ошибки.

> [!NOTE]
> Не используйте этот метод, чтобы завершить работу приложения Microsoft Store или [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] приложения, за исключением сценариев тестирования или отладки. Программный или пользовательского интерфейса способов закрыть приложение магазина, не разрешено согласно [банка политики](/legal/windows/agreements/store-policies). Дополнительные сведения см. в разделе [жизненный цикл приложения UWP](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Синтаксис

```c
void abort( void );
```

## <a name="return-value"></a>Возвращаемое значение

`abort` не возвращает управление вызывающему процессу. По умолчанию он проверяет наличие обработчика прерывания сигнала и вызывает `SIGABRT`, если он задан. Затем `abort` завершает текущий процесс и возвращает код выхода для родительского процесса.

## <a name="remarks"></a>Примечания

**Блок, относящийся только к системам Microsoft**

По умолчанию при сборке приложения с использованием отладочной библиотеки среды выполнения подпрограмма `abort` выдает сообщение об ошибке, прежде чем появляется `SIGABRT`. Для консольных приложений, работающих в режиме консоли, отправляется сообщение в `STDERR`. Классические приложения Windows и консольные приложения, запускаемые в окнах, отображают сообщение в окне сообщений. Чтобы отключить сообщение, снимите флаг `_WRITE_ABORT_MSG` с помощью функции [_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md). Отображаемое сообщение зависит от версии используемой среды выполнения. Для приложений, построенных с помощью последних версий Visual C++ сообщение выглядит следующим образом:

> R6010 - abort() вызова

В предыдущих версиях библиотеки среды выполнения C отображается следующее сообщение:

> Это приложение запросило завершение среды выполнения необычным способом. За дополнительной информацией обращайтесь в службу поддержки приложения.

При компиляции программы в режиме отладки в окне сообщения отображаются параметры **Прервать**, **Повторить** или **Пропустить**. Если пользователь выбирает параметр **Прервать**, программа немедленно завершается и возвращает код выхода 3. Если пользователь выбирает параметр **Повторить**, вызывается отладчик (если он доступен) для JIT-отладки. Если пользователь выбирает параметр **Пропустить**, `abort` продолжает работу в обычном режиме.

Затем и в окончательной, и в отладочной сборке `abort` проверяет, задает ли обработчик прерывания сигнала. Если задан обработчик сигнала, не используемый по умолчанию, `abort` вызывает `raise(SIGABRT)`. С помощью функции [signal](../../c-runtime-library/reference/signal.md) свяжите функцию обработчика сигналов прерывания с сигналом `SIGABRT`. Вы можете выполнить пользовательские действия — например, освободить ресурсы или записать данные сведений — и завершить работу приложения с кодом ошибки в функции обработчика. Если пользовательский обработчик сигналов не определен, `abort` не вызывает сигнал `SIGABRT`.

По умолчанию в неотладочных сборках приложений рабочего стола или консоль `abort` затем вызывает механизм службы отчетов об ошибках Windows (прежнее название — аварийного восстановления. Watson), передающий корпорации Майкрософт отчеты о сбоях. Это поведение можно включить или отключить, вызвав `_set_abort_behavior` и задав или замаскировав флаг `_CALL_REPORTFAULT`. Если флаг установлен, в Windows появится окно сообщения, содержащее текст вида "Возникшая проблема привела к прекращению работы программы". Пользователь может вызвать отладчик с помощью кнопки **Отладка** или нажать кнопку **Закрыть программу**, чтобы завершить приложение с кодом ошибки, который определяется операционной системой.

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

## <a name="see-also"></a>См. также

[Использование abort](../../cpp/using-abort.md)  
[Функция abort](../../c-language/abort-function-c.md)  
[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)  
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)  
[exit, _Exit, _exit](../../c-runtime-library/reference/exit-exit-exit.md)  
[raise](../../c-runtime-library/reference/raise.md)  
[signal](../../c-runtime-library/reference/signal.md)  
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)  
[_DEBUG](../../c-runtime-library/debug.md)  
[_set_abort_behavior](../../c-runtime-library/reference/set-abort-behavior.md)  

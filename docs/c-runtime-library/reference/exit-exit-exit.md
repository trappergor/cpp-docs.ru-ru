---
title: "exit, _Exit, _exit | Документы Майкрософт"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _exit
- exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed4835662a53f3cb19b47818a9d6adfb3dfb2930
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="exit-exit-exit"></a>exit, _Exit, _exit

Завершает вызывающий процесс. Функция `exit` завершает его после очистки; `_exit` и `_Exit` завершают его мгновенно.

> [!NOTE]
> Не используйте этот метод, чтобы завершить работу приложения универсальной платформы Windows (UWP), за исключением сценариев тестирования или отладки. Программный или пользовательского интерфейса способов закрыть приложение магазина, не разрешено согласно [банка политики](/legal/windows/agreements/store-policies). Дополнительные сведения см. в разделе [жизненный цикл приложения UWP](/windows/uwp/launch-resume/app-lifecycle). Дополнительные сведения о приложениях Windows 10 см. в разделе [Практические руководства для приложений Windows 10](http://go.microsoft.com/fwlink/p/?linkid=619133).

## <a name="syntax"></a>Синтаксис

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit( 
   int const status
);
```

### <a name="parameters"></a>Параметры

_status_  
Код состояния завершения.

## <a name="remarks"></a>Примечания

Функции `exit`, `_Exit` и `_exit` завершают вызывающий процесс. Функция `exit` вызывает деструкторы для объектов локального потока, а затем вызывает в порядке "последним пришел — первым вышел" (LIFO) функции, зарегистрированные `atexit` и `_onexit`, а затем очищает все файловые буферы перед завершением процесса. Функции `_Exit` и `_exit` завершают процесс без удаления объектов локального потока или обработки функций `atexit` или `_onexit` , а также без очистки буферов потока.

Несмотря на то что `exit`, `_Exit` и `_exit` вызовы не возвращают значение, значение в _состояние_ становится доступным среде узла или ожидающему вызывающему процессу, если такой существует, после завершения процесса. Как правило, вызывающая функция задает _состояние_ значение 0 для указания нормального завершения или принимает другое значение для указания ошибки. _Состояние_ значение не станет доступным для операционной системы пакетной команды `ERRORLEVEL` и представлено одной из двух констант: `EXIT_SUCCESS`, которая представляет значение 0, или `EXIT_FAILURE`, которая представляет значение 1.

Функции `exit`, `_Exit`, `_exit`, `quick_exit`, `_cexit`и `_c_exit` ведут себя следующим образом.

|Функция|Описание:|
|--------------|-----------------|
|`exit`|Выполняет полные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|`_Exit`|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|`_exit`|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|`quick_exit`|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|`_cexit`|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|
|`_c_exit`|Выполняет минимальные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|

При вызове функции `exit`,  `_Exit` или `_exit` деструкторы для любых существующих во время вызова временных или автоматических объектов не вызываются. Автоматический объект — это локальный объект статическим, определенные в функции. Временный объект — это объект, создаваемый компилятором, такие как значения, возвращенного при вызове функции. Чтобы удалить автоматический объект перед вызовом `exit`, `_Exit`, или `_exit`, явным образом вызовите деструктор объекта, как показано ниже:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Не используйте `DLL_PROCESS_ATTACH` для вызова `exit` из `DllMain`. Чтобы выйти из `DLLMain` функционировать, возвращают `FALSE` из `DLL_PROCESS_ATTACH`.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|`exit`, `_Exit`, `_exit`|\<process.h> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)  
[abort](../../c-runtime-library/reference/abort.md)  
[atexit](../../c-runtime-library/reference/atexit.md)  
[_cexit, _c_exit](../../c-runtime-library/reference/cexit-c-exit.md)  
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)  
[_onexit, _onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)  
[quick_exit](../../c-runtime-library/reference/quick-exit1.md)  
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)  
[system, _wsystem](../../c-runtime-library/reference/system-wsystem.md)  

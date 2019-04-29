---
title: exit, _Exit, _exit
ms.date: 1/02/2018
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
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.openlocfilehash: 7b2a22649d779f382bb4055b1e44c14312627ccd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339355"
---
# <a name="exit-exit-exit"></a>exit, _Exit, _exit

Завершает вызывающий процесс. **Выйти из** функция завершает его после очистки; **_exit** и **_Exit** завершают его мгновенно.

> [!NOTE]
> Не используйте этот метод, чтобы завершить работу приложения универсальной платформы Windows (UWP), за исключением сценариев тестирования или отладки. Закрытие приложения Store способов программным способом или пользовательского интерфейса не разрешены согласно [политики Microsoft Store](/legal/windows/agreements/store-policies). Дополнительные сведения см. в разделе [жизненного цикла приложения универсальной платформы Windows](/windows/uwp/launch-resume/app-lifecycle). Дополнительные сведения о приложениях Windows 10 см. в разделе [Практические руководства для приложений Windows 10](https://developer.microsoft.com/windows/apps).

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

*status*<br/>
Код состояния завершения.

## <a name="remarks"></a>Примечания

**Выйти из**, **_Exit** и **_exit** функции завершают вызывающий процесс. **Выйти из** функция вызывает деструкторы для объектов локального потока, затем вызывает — в порядке (LIFO) последнего in-first-out — функции, зарегистрированные с **atexit** и **_onexit**, а затем сбрасывает все файловые буферы перед завершением процесса. **_Exit** и **_exit** функции завершают процесс без удаления объектов локального потока или обработки **atexit** или **_onexit**функции, а также без очистки буферов потоков.

Несмотря на то что **выйти из**, **_Exit** и **_exit** вызовы не возвращают значение, значение в *состояние* становится доступным среде узла или ожидающих вызывающему процессу, если таковой существует, после завершения процесса. Как правило, вызывающая функция задает *состояние* значение 0 для указания нормального завершения или принимает другое значение для указания ошибки. *Состояние* значение доступно в команду операционной системы пакета **ERRORLEVEL** и представлено одной из двух констант: **EXIT_SUCCESS**, который представляет значение 0, или **EXIT_FAILURE**, который представляет значение 1.

**Выйти из**, **_Exit**, **_exit**, **quick_exit**, **_cexit**, и **_c_exit** функции ведут себя следующим образом.

|Функция|Описание|
|--------------|-----------------|
|**exit**|Выполняет полные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_Exit**|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_exit**|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**quick_exit**|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_cexit**|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|
|**_c_exit**|Выполняет минимальные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|

При вызове **выйти из**, **_Exit** или **_exit** функции, деструкторы для любых существующих во время вызова временных или автоматических объектов не вызываются. Автоматический объект — это локальный объект статическим, определенные в функции. Временный объект — это объект, создаваемый компилятором, такие как значение, возвращаемое в результате вызова функции. Чтобы удалить автоматический объект перед вызовом метода **выйти из**, **_Exit**, или **_exit**, явным образом вызовите деструктор объекта, как показано ниже:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Не используйте **DLL_PROCESS_ATTACH** для вызова **выйти из** из **DllMain**. Чтобы выйти из **DLLMain** функции, возвращается **FALSE** из **DLL_PROCESS_ATTACH**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**exit**, **_Exit**, **_exit**|\<process.h> или \<stdlib.h>|

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

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

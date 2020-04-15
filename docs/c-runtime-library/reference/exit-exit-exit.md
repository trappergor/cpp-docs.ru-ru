---
title: exit, _Exit, _exit
ms.date: 4/2/2020
api_name:
- _exit
- exit
- _o__exit
- _o_exit
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 5bdb5ff5c8309e03a49f9518f65a45d5757e9bfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347637"
---
# <a name="exit-_exit-_exit"></a>exit, _Exit, _exit

Завершает вызывающий процесс. Функция **выхода** завершает его после очистки; **_exit** и **_Exit** немедленно прекратите его.

> [!NOTE]
> Не используйте этот метод для закрытия приложения Universal Windows Platform (UWP), за исключением сценариев тестирования или отладки. Программные или утилиты для использования не допускаются в соответствии с [правилами Microsoft Store.](/legal/windows/agreements/store-policies) Для получения дополнительной [UWP App lifecycle](/windows/uwp/launch-resume/app-lifecycle)информации см. Дополнительные сведения о приложениях Windows 10 см. в разделе [Практические руководства для приложений Windows 10](https://developer.microsoft.com/windows/apps).

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

*состояние*<br/>
Код состояния завершения.

## <a name="remarks"></a>Remarks

Функции **выхода,** **_Exit** и **_exit** прекращаются процесс омрачанием. Функция **выхода** вызывает деструкторов для объектов локального потока, затем вызывает - в порядке последнего выхода (LIFO) - функции, зарегистрированные **atexit** и **_onexit,** а затем сбрасывает все буферы файлов до завершения процесса. **функции _Exit** и **_exit** прекращают процесс, не разрушая локальные объекты потока или обрабатывая **функции atexit** или **_onexit** и не промывая буферы потока.

Хотя **выход,** **_Exit** и **_exit** вызовы не возвращают значение, значение в *статусе* становится доступным для среды узла или процесса ожидания вызова, если он существует, после выхода процесса. Обычно вызывающее значение значения *состояния* устанавливается до 0 для обозначения нормального выхода или к какому-либо другому значению для обозначения ошибки. Значение *статуса* доступно для команды пакетной системы **неподействующий ERRORLEVEL** и представлено одной из двух констант: **EXIT_SUCCESS,** что представляет собой значение 0 или **EXIT_FAILURE,** что означает значение 1.

**Выход,** **_Exit,** **_exit,** **quick_exit,** **_cexit,** и **_c_exit** функции ведут себя следующим образом.

|Компонент|Описание|
|--------------|-----------------|
|**Выход**|Выполняет полные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_Exit**|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_exit**|Выполняет минимальные процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**quick_exit**|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и предоставляет полученный код состояния среде узла.|
|**_cexit**|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|
|**_c_exit**|Выполняет минимальные процедуры завершения библиотеки C и возвращает управление вызывающему объекту. Не завершает процесс.|

При вызове **выхода,** **_Exit** или **_exit** функции, деструкторов для любых временных или автоматических объектов, которые существуют во время вызова не называются. Автоматический объект — это нестатический локальный объект, определяемый в функции. Временный объект — это объект, созданный компилятором, например значение, возвращаемые вызовом функции. Чтобы уничтожить автоматический объект перед вызовом **выхода,** **_Exit**или **_exit,** явно вызов уничтожайте объект, как показано здесь:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

Не используйте **DLL_PROCESS_ATTACH** для вызова **выхода** из **DllMain**. Чтобы выйти из функции **DLLMain,** верните **FALSE** из **DLL_PROCESS_ATTACH.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**выход,** **_Exit,** **_exit**|\<process.h> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Прервать](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec функции](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

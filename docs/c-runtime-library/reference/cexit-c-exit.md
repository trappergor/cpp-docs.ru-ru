---
title: _cexit, _c_exit
ms.date: 4/2/2020
api_name:
- _c_exit
- _cexit
- _o__cexit
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
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: 9eb856efca054423465aa7d30092edaf83a65eeb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333534"
---
# <a name="_cexit-_c_exit"></a>_cexit, _c_exit

Выполняет операции очистки и возвращает значение, не прерывая процесс.

## <a name="syntax"></a>Синтаксис

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Remarks

**_cexit** функция вызывает, в последнем, первом из (LIFO) порядке, функции, зарегистрированные **atexit** и **_onexit**. Затем **_cexit** сбрасывает все буферы ввоза и закрывает все открытые потоки перед возвращением. **_c_exit** такой же, как **_exit** но возвращается к процессу вызова без обработки **atexit** или **_onexit** или промывки буферов потока. Поведение **выхода,** **_exit,** **_cexit**и **_c_exit** показано в следующей таблице.

|Компонент|Поведение|
|--------------|--------------|
|**Выход**|Выполняет полные процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|
|**_exit**|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|
|**_cexit**|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|
|**_c_exit**|Выполняет быстрые процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|

При вызове **_cexit** или **_c_exit** функций, деструкторов для любых временных или автоматических объектов, которые существуют во время вызова не называются. Автоматический объект — это объект, который определяется в функции, если он не объявлен статическим. Временный объект — это объект, созданный компилятором. Чтобы уничтожить автоматический объект перед вызовом **_cexit** или **_c_exit,** явно позвоните в деструктор объекта следующим образом:

```cpp
myObject.myClass::~myClass( );
```

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Прервать](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec функции](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

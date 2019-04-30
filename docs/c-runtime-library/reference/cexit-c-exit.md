---
title: _cexit, _c_exit
ms.date: 11/04/2016
apiname:
- _c_exit
- _cexit
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
ms.openlocfilehash: a075e8a8e965a195765b86ffa21fed0915dbf5ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335494"
---
# <a name="cexit-cexit"></a>_cexit, _c_exit

Выполняет операции очистки и возвращает значение, не прерывая процесс.

## <a name="syntax"></a>Синтаксис

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Примечания

**_Cexit** вызовы функций, в последний на входе, порядка поступления (LIFO), функции, зарегистрированные **atexit** и **_onexit**. Затем **_cexit** очищает все буферы ввода-вывода и закрывает все открытые потоки перед возвратом. **_c_exit** совпадает со значением **_exit** , но возвращает вызывающему процессу без обработки **atexit** или **_onexit** либо очистки буферов потоков. Поведение **выйти из**, **_exit**, **_cexit**, и **_c_exit** показано в следующей таблице.

|Функция|Поведение|
|--------------|--------------|
|**exit**|Выполняет полные процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|
|**_exit**|Выполняет быстрые процедуры завершения библиотеки C, завершает процесс и завершается с предоставленным кодом состояния.|
|**_cexit**|Выполняет полные процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|
|**_c_exit**|Выполняет быстрые процедуры завершения библиотеки C и возвращает управление вызывающему объекту, но не завершает процесс.|

При вызове **_cexit** или **_c_exit** функции, деструкторы для любых существующих во время вызова временных или автоматических объектов не вызываются. Автоматический объект — это объект, который определяется в функции, если он не объявлен статическим. Временный объект — это объект, созданный компилятором. Чтобы удалить автоматический объект перед вызовом **_cexit** или **_c_exit**, явным образом вызовите деструктор объекта следующим образом:

```cpp
myObject.myClass::~myClass( );
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>

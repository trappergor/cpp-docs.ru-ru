---
title: _cexit _c_exit | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0840ccec85d46a13984b65ebe99e53b968bedeb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cexit-cexit"></a>_cexit, _c_exit

Выполняет операции очистки и возвращает значение, не прерывая процесс.

## <a name="syntax"></a>Синтаксис

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Примечания

**_Cexit** вызовы функций, в последней в порядке поступления (LIFO), функции, зарегистрированные **atexit** и **_onexit**. Затем **_cexit** очищает все буферы ввода-вывода и закрытие всех открытых потоков перед возвратом. **_c_exit** совпадает со значением **_exit** , но возвращает вызывающему процессу без обработки **atexit** или **_onexit** или очистки буферов потока. Поведение **выхода**, **_exit**, **_cexit**, и **_c_exit** показано в следующей таблице.

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

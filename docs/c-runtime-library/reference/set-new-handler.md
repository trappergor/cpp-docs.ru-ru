---
title: _set_new_handler
ms.date: 4/2/2020
api_name:
- _set_new_handler
- _o__set_new_handler
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
- _set_new_handler
- set_new_handler
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
ms.openlocfilehash: c3f1b9bd8bf2a4404e2239858e4c3c59b755bacd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332374"
---
# <a name="_set_new_handler"></a>_set_new_handler

Передает управление механизму обработки ошибок, если оператору **new** не удается выделить память.

## <a name="syntax"></a>Синтаксис

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Параметры

*pNewHandler*<br/>
Указатель на предоставленную приложением функцию обработки памяти. Аргумент 0 вызывает удаление нового обработчика.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию обработки исключений, зарегистрированную **_set_new_handler,** так что предыдущая функция может быть восстановлена позже. Если предыдущая функция не установлена, значение возврата может быть использовано для восстановления поведения по умолчанию; это значение может быть **NULL**.

## <a name="remarks"></a>Remarks

Функция **_set_new_handler** СЗ определяет функцию обработки исключений, которая получает контроль, если **новый** оператор не выделяет память. При **сходе сбоя** система выполнения автоматически вызывает функцию обработки исключений, которая была передана в качестве аргумента **для _set_new_handler.** **_PNH,** определяется в New.h, является указателем на функцию, которая возвращает **введите Int** и принимает аргумент типа **size_t.** Используйте **size_t,** чтобы указать количество места, которое будет выделено.

Обработчик по умолчанию отсутствует.

**_set_new_handler,** по сути, схема сбора мусора. Система времени выполнения делает попытку выделения памяти каждый раз, когда пользовательская функция возвращает ненулевое значение, и завершается неудачей, если пользовательская функция возвращает 0.

Возникновение **функции _set_new_handler** в программе регистрирует функцию обработки исключений, указанную в списке аргументов с системой времени выполнения:

```cpp
// set_new_handler1.cpp
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#include <new.h>

int handle_program_memory_depletion( size_t )
{
   // Your code
}

int main( void )
{
   _set_new_handler( handle_program_memory_depletion );
   int *pi = new int[BIG_NUMBER];
}
```

Можно сохранить адрес функции, который в последний раз был передан **функции _set_new_handler** функции, и восстановить его позже:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

Функция [_set_new_mode](set-new-mode.md) C++ задает новый режим обработчика для [malloc](malloc.md). Новый режим обработчика указывает, является ли, при сбое, **malloc** является вызов новой рутины обработчика, как установить **_set_new_handler.** По умолчанию **malloc** не вызывает новую рутину обработчика при неспособности выделить память. Вы можете переопределить это поведение по умолчанию, так что, когда **malloc** не выделяет память, **malloc** вызывает новую рутину обработчика так же, как **новый** оператор делает, когда он не по той же причине. Чтобы переопределить значение по умолчанию, вызовите:

```cpp
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием Newmode.obj.

При предоставлении `operator new` данных о пользовательских функциях новые функции обработчика автоматически не вызываются при сбое.

Дополнительные сведения см. в разделе [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md) в *Справочнике по языку C++*.

Существует единый **обработчик _set_new_handler** для всех динамически связанных DLLs или исполняемых; даже если вы **звоните _set_new_handler** ваш обработчик может быть заменен другим или что вы заменяете обработчик, установленный другим DLL или исполняемым.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В этом примере если выделение памяти завершается сбоем, управление передается обработчику MyNewHandler. Аргумент, переданный обработчику MyNewHandler, представляет собой запрошенное количество байтов. Значение, возвращаемое из MyNewHandler, представляет собой флаг, указывающий, нужна ли повторная попытка выделения памяти: ненулевое значение указывает, что выделение должно быть повторено, нулевое значение указывает, что произошла ошибка выделения памяти.

```cpp
// crt_set_new_handler.cpp
// compile with: /c
#include <stdio.h>
#include <new.h>
#define BIG_NUMBER 0x1fffffff

int coalesced = 0;

int CoalesceHeap()
{
   coalesced = 1;  // Flag RecurseAlloc to stop
   // do some work to free memory
   return 0;
}
// Define a function to be called if new fails to allocate memory.
int MyNewHandler( size_t size )
{
   printf("Allocation failed. Coalescing heap.\n");

   // Call a function to recover some heap space.
   return CoalesceHeap();
}

int RecurseAlloc() {
   int *pi = new int[BIG_NUMBER];
   if (!coalesced)
      RecurseAlloc();
   return 0;
}

int main()
{
   // Set the failure handler for new to be MyNewHandler.
   _set_new_handler( MyNewHandler );
   RecurseAlloc();
}
```

```Output
Allocation failed. Coalescing heap.

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Бесплатный](free.md)<br/>
[realloc](realloc.md)<br/>

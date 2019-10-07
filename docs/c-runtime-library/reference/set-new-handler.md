---
title: _set_new_handler
ms.date: 11/04/2016
api_name:
- _set_new_handler
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
ms.openlocfilehash: a1f340887efd657dd9ff9bf219534d77fdd90aa3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948470"
---
# <a name="_set_new_handler"></a>_set_new_handler

Передает управление механизму обработки ошибок, если оператору **new** не удается выделить память.

## <a name="syntax"></a>Синтаксис

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Параметры

*пневхандлер*<br/>
Указатель на предоставленную приложением функцию обработки памяти. Аргумент 0 вызывает удаление нового обработчика.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию обработки исключений, зарегистрированную в **_set_new_handler**, чтобы предыдущую функцию можно было восстановить позже. Если Предыдущая функция не задана, возвращаемое значение можно использовать для восстановления поведения по умолчанию. Это значение может быть **равно NULL**.

## <a name="remarks"></a>Примечания

C++ Функция **_set_new_handler** указывает функцию обработки исключений, которая получает управление, если оператору **New** не удается выделить память. Если **Новая** ошибка не возникает, система времени выполнения автоматически вызывает функцию обработки исключений, которая была передана в качестве аргумента в **_set_new_handler**. **_PNH**, определенный в New. h, является указателем на функцию, возвращающую тип **int** и принимающую аргумент типа **size_t**. Используйте **size_t** , чтобы указать объем выделяемого пространства.

Обработчик по умолчанию отсутствует.

**_set_new_handler** — это, по сути, схема сбора мусора. Система времени выполнения делает попытку выделения памяти каждый раз, когда пользовательская функция возвращает ненулевое значение, и завершается неудачей, если пользовательская функция возвращает 0.

Вхождение функции **_set_new_handler** в программу регистрирует функцию обработки исключений, указанную в списке аргументов, с системой времени выполнения:

```cpp
// set_new_handler1.cpp
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

Вы можете сохранить адрес функции, который был в последний раз передан функции **_set_new_handler** , и восстановить его позже:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

Функция [_set_new_mode](set-new-mode.md) C++ задает новый режим обработчика для [malloc](malloc.md). Новый режим обработчика указывает, что в случае сбоя **malloc** вызывает новую подпрограммы обработчика, заданную **_set_new_handler**. По умолчанию **malloc** не вызывает новую подпрограммы обработчика при сбое выделения памяти. Это поведение по умолчанию можно переопределить таким образом, что, когда **malloc** не сможет выделить память, **malloc** вызывает новую подпрограммы обработчика так же, как и оператор **New** в случае сбоя по той же причине. Чтобы переопределить значение по умолчанию, вызовите:

```cpp
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием Newmode.obj.

Если предоставлено определенное `operator new` пользователем значение, новые функции обработчика не вызываются автоматически при сбое.

Дополнительные сведения см. в разделе [new](../../cpp/new-operator-cpp.md) и [delete](../../cpp/delete-operator-cpp.md) в *Справочнике по языку C++* .

Существует один обработчик **_set_new_handler** для всех динамически связанных DLL-библиотек или исполняемых файлов. даже при вызове **_set_new_handler** обработчик может быть заменен другим или заменять обработчик, заданный другой библиотекой DLL или исполняемым файлом.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>

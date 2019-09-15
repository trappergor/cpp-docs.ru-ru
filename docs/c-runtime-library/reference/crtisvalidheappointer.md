---
title: _CrtIsValidHeapPointer
ms.date: 11/04/2016
api_name:
- _CrtIsValidHeapPointer
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
ms.openlocfilehash: 9a8746eb2da90ac5515d92113b977011a4647fe6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942386"
---
# <a name="_crtisvalidheappointer"></a>_CrtIsValidHeapPointer

Проверяет, находится ли заданный указатель в куче, выделенной определенной библиотекой среды выполнения C, но не обязательно библиотекой CRT вызывающей функции. В версиях CRT, выпущенных до выхода Visual Studio 2010, эта функция проверяла, находится ли заданный указатель в локальной куче (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtIsValidHeapPointer(
   const void *userData
);
```

### <a name="parameters"></a>Параметры

*userData*<br/>
Указатель на начало выделенного блока памяти.

## <a name="return-value"></a>Возвращаемое значение

**_CrtIsValidHeapPointer** возвращает значение true, если указанный указатель находится в куче, совместно используемой всеми экземплярами библиотеки CRT. В версиях CRT, выпущенных до выхода Visual Studio 2010, эта функция возвращала значение TRUE, если указатель находился в локальной куче. В противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

Использовать эту функцию не рекомендуется. Начиная с библиотеки CRT в Visual Studio 2010, все библиотеки CRT используют одну и ту же кучу операционной системы — *кучу процесса*. Функция **_CrtIsValidHeapPointer** сообщает, выделен ли указатель в куче CRT, но не в том, что она была выделена библиотекой CRT вызывающей стороны. Возьмем для примера блок, выделенный с помощью библиотеки CRT в составе Visual Studio 2010. Если функция **_CrtIsValidHeapPointer** , экспортируемая с помощью версии библиотеки CRT для Visual Studio 2012, проверяет указатель, возвращается значение true. Необходимости в такой проверке больше нет. В версиях библиотеки CRT до Visual Studio 2010 эта функция используется для проверки наличия того или иного адреса памяти в локальной куче. Локальная куча обращается к куче, созданной и управляемой определенным экземпляром библиотеки среды выполнения C. Если библиотека динамической компоновки (DLL) содержит статическую ссылку на библиотеку среды выполнения, она имеет свой собственный экземпляр кучи среды выполнения, а значит и собственную кучу, не зависящую от локальной кучи приложения. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtIsValidHeapPointer** удаляются во время предварительной обработки.

Так как эта функция возвращает значение TRUE или FALSE, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Приведенный ниже пример вызывает сбой утверждения, если указанный адрес находится не в локальной куче.

```C
_ASSERTE( _CrtIsValidHeapPointer( userData ) );
```

Дополнительные сведения о том, как **_CrtIsValidHeapPointer** можно использовать с другими функциями и макросами отладки, см. в разделе [macros for Reporting](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtIsValidHeapPointer**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

В приведенном ниже примере показано, как проверить допустимость памяти, если используется библиотека среды выполнения C до Visual Studio 2010. Пример приведен для пользователей предыдущих версий библиотеки кодов CRT.

```C
// crt_isvalid.c
// This program allocates a block of memory using _malloc_dbg
// and then tests the validity of this memory by calling
// _CrtIsMemoryBlock,_CrtIsValidPointer, and _CrtIsValidHeapPointer.

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

#define  TRUE   1
#define  FALSE  0

int main( void )
{
    char *my_pointer;

    // Call _malloc_dbg to include the filename and line number
    // of our allocation request in the header information
    my_pointer = (char *)_malloc_dbg( sizeof(char) * 10,
        _NORMAL_BLOCK, __FILE__, __LINE__ );

    // Ensure that the memory got allocated correctly
    _CrtIsMemoryBlock((const void *)my_pointer, sizeof(char) * 10,
        NULL, NULL, NULL );

    // Test for read/write accessibility
    if (_CrtIsValidPointer((const void *)my_pointer,
        sizeof(char) * 10, TRUE))
        printf("my_pointer has read and write accessibility.\n");
    else
        printf("my_pointer only has read access.\n");

    // Make sure my_pointer is within the local heap
    if (_CrtIsValidHeapPointer((const void *)my_pointer))
        printf("my_pointer is within the local heap.\n");
    else
        printf("my_pointer is not located within the local"
               " heap.\n");

    free(my_pointer);
}
```

```Output
my_pointer has read and write accessibility.
my_pointer is within the local heap.
```

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>

---
title: _CrtSetBreakAlloc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtSetBreakAlloc
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
apitype: DLLExport
f1_keywords:
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs:
- C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e14e1d40d5d20b9759d115eaf2fd29b3cae57172
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc

Задает точку останова для указанного порядкового номера выделения объекта (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
long _CrtSetBreakAlloc(
   long lBreakAlloc
);
```

### <a name="parameters"></a>Параметры

*lBreakAlloc*<br/>
Порядковый номер выделения, для которого задается точка останова.

## <a name="return-value"></a>Возвращаемое значение

Возвращает предыдущий порядковый номер выделения объекта, для которого задана точка останова.

## <a name="remarks"></a>Примечания

**_CrtSetBreakAlloc** позволяет приложению выполнять обнаружение утечки памяти путем останова в определенной точке выделения памяти и обратной трассировки до источника запроса. Функция использует последовательный порядковый номер выделения объекта, назначенный блоку памяти во время выделения в куче. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtSetBreakAlloc** удаляются на этапе предварительной обработки.

Порядковый номер выделения объекта хранится в поле *lRequest* структуры **_CrtMemBlockHeader**, определенной в Crtdbg.h. Когда данные о блоке памяти включаются в отчет одной из функций дампа отладки, этот номер заключается в фигурные скобки (например, {36}).

Дополнительные сведения о том, как **_CrtSetBreakAlloc** можно использовать с другими функции управления памятью см. в разделе [отслеживание запросов выделения кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtSetBreakAlloc**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_setbrkal.c
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug

/*
* In this program, a call is made to the _CrtSetBreakAlloc routine
* to verify that the debugger halts program execution when it reaches
* a specified allocation number.
*/

#include <malloc.h>
#include <crtdbg.h>

int main( )
{
        long allocReqNum;
        char *my_pointer;

        /*
         * Allocate "my_pointer" for the first
         * time and ensure that it gets allocated correctly
         */
        my_pointer = malloc(10);
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);

        /*
         * Set a breakpoint on the allocation request
         * number for "my_pointer"
         */
        _CrtSetBreakAlloc(allocReqNum+2);

        /*
         * Alternate freeing and reallocating "my_pointer"
         * to verify that the debugger halts program execution
         * when it reaches the allocation request
         */
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
}
```

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>

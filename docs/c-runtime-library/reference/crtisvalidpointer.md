---
title: _CrtIsValidPointer | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
dev_langs:
- C++
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb78f8dee494fd213df6db16e2800cb9090bdf3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397279"
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer

Проверяет, не равен ли указатель нулю. В версиях библиотеки времени выполнения языка C, выпущенных до выхода Visual Studio 2010, проверяет, является ли указанный диапазон памяти допустимым для чтения и записи (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>Параметры

*address*<br/>
Указывает начало диапазона памяти для проверки.

*size*<br/>
Размер указанного диапазона памяти (в байтах).

*access*<br/>
Доступ на чтение или запись для определения диапазона памяти.

## <a name="return-value"></a>Возвращаемое значение

**_CrtIsValidPointer** возвращает TRUE, если заданный указатель не имеет значение null. В версиях библиотеки CRT, выпущенных до выхода Visual Studio 2010, возвращает значение TRUE, если диапазон памяти допустим для указанной операции или операций. В противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

Начиная с библиотеки CRT в Visual Studio 2010 *размер* и *доступа* параметры учитываются, и **_CrtIsValidPointer** только проверяет, что указанный *адрес* не имеет значение null. Поскольку этот тест легко выполняется вручную, не рекомендуем использовать данную функцию. В версиях до Visual Studio 2010, эта функция проверяет диапазон памяти, начиная с *адрес* и расширение для *размер* байт является допустимым для указанной операции или операций доступа. Когда *доступа* имеет значение TRUE, диапазон памяти проверяется для чтения и записи. Когда *доступа* имеет значение FALSE, диапазон памяти проверяется только для чтения. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtIsValidPointer** удаляются на этапе предварительной обработки.

Так как эта функция возвращает значение TRUE или FALSE, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Следующий пример вызывает сбой утверждения, если диапазон памяти недопустим для операций чтения и записи.

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

Дополнительные сведения о том, как **_CrtIsValidPointer** можно использовать с другими функциями и макросами отладки см. в разделе [макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h>|

**_CrtIsValidPointer** является расширением Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

См. пример для раздела [_CrtIsValidHeapPointer](crtisvalidheappointer.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>

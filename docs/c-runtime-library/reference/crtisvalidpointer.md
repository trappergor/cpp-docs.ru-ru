---
title: _CrtIsValidPointer
ms.date: 11/04/2016
api_name:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
ms.openlocfilehash: 490d2dea097935dee2cd2a003aa28e32f1ced69d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938772"
---
# <a name="_crtisvalidpointer"></a>_CrtIsValidPointer

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

**_CrtIsValidPointer** возвращает значение true, если указанный указатель не равен null. В версиях библиотеки CRT, выпущенных до выхода Visual Studio 2010, возвращает значение TRUE, если диапазон памяти допустим для указанной операции или операций. В противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

Начиная с библиотеки CRT в Visual Studio 2010 параметры *size* и *Access* игнорируются, а **_CrtIsValidPointer** проверяет только то, что указанный *адрес* не равен null. Поскольку этот тест легко выполняется вручную, не рекомендуем использовать данную функцию. В версиях до Visual Studio 2010 функция проверяет, что диапазон памяти, начинающийся с *адреса* , и расширяется на *Размер* байтов, допустим для указанной операции или операций специальных возможностей. Если для параметра *Access* ЗАДАНО значение true, диапазон памяти проверяется как для чтения, так и для записи. Если *доступ* имеет значение false, диапазон памяти проверяется только для чтения. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtIsValidPointer** удаляются во время предварительной обработки.

Так как эта функция возвращает значение TRUE или FALSE, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Следующий пример вызывает сбой утверждения, если диапазон памяти недопустим для операций чтения и записи.

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

Дополнительные сведения о том, как **_CrtIsValidPointer** можно использовать с другими функциями и макросами отладки, см. в разделе [macros for Reporting](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h>|

**_CrtIsValidPointer** — это расширение Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

См. пример для раздела [_CrtIsValidHeapPointer](crtisvalidheappointer.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>

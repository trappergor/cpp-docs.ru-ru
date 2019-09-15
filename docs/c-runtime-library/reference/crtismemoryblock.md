---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
api_name:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: f29745acd06f6f5b3fa96367444e800bdc3e8e3a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938737"
---
# <a name="_crtismemoryblock"></a>_CrtIsMemoryBlock

Проверяет, находится ли указанный блок памяти в локальной куче и имеет ли он действительный идентификатор типа блока отладочной кучи (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C
int _CrtIsMemoryBlock(
   const void *userData,
   unsigned int size,
   long *requestNumber,
   char **filename,
   int *linenumber
);
```

### <a name="parameters"></a>Параметры

*userData*<br/>
Указатель на начало блока памяти, требующего проверки.

*size*<br/>
Размер указанного блока в байтах.

*рекуестнумбер*<br/>
Указатель на номер выделения блока или **значение NULL**.

*filename*<br/>
Указатель на имя исходного файла, который запросил блок, или **значение NULL**.

*linenumber*<br/>
Указатель на номер строки в исходном файле или **значение NULL**.

## <a name="return-value"></a>Возвращаемое значение

**_CrtIsMemoryBlock** возвращает **значение true** , если указанный блок памяти находится в локальной куче и имеет допустимый идентификатор типа блока отладочной кучи. в противном случае функция возвращает **значение false**.

## <a name="remarks"></a>Примечания

Функция **_CrtIsMemoryBlock** проверяет, что указанный блок памяти находится в локальной куче приложения и имеет допустимый идентификатор типа блока. Эту функцию можно также использовать для получения порядкового номера распределения объекта, а также имени или номера строки исходного файла, содержащего исходный запрос на выделение блока памяти. Передача значений, отличных от**null** , для параметров *рекуестнумбер*, *filename*или *LineNumber* приводит к тому, что **_CrtIsMemoryBlock** задает значения этих параметров в заголовке отладки блока памяти, если он находит блок в Локальная куча. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtIsMemoryBlock** удаляются во время предварительной обработки.

Если **_CrtIsMemoryBlock** завершается сбоем, возвращается **значение false** , а выходные параметры инициализируются значениями по умолчанию: *рекуестнумбер* и **LineNumber** имеют значение 0, а *filename* имеет значение **null**.

Так как эта функция возвращает значение **TRUE** или **FALSE**, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Приведенный ниже пример вызывает сбой утверждения, если указанный адрес находится не в локальной куче.

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Дополнительные сведения о том, как **_CrtIsMemoryBlock** можно использовать с другими функциями и макросами отладки, см. в разделе [macros for Reporting](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

См. пример для раздела [_CrtIsValidHeapPointer](crtisvalidheappointer.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>

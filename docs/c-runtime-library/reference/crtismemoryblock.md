---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
apiname:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: c4a85ebeb45552c6f5355853de2a45766d6bc984
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339901"
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock

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

*requestNumber*<br/>
Указатель на номер выделения блока или **NULL**.

*filename*<br/>
Указатель на имя исходного файла, который запрашивает блок или **NULL**.

*linenumber*<br/>
Указатель на номер строки в исходном файле или **NULL**.

## <a name="return-value"></a>Возвращаемое значение

**_CrtIsMemoryBlock** возвращает **TRUE** Если указанный блок памяти находится в локальной куче и имеет допустимый идентификатор блока отладочной кучи типа; в противном случае функция в дополнительной возвращает **FALSE**.

## <a name="remarks"></a>Примечания

**_CrtIsMemoryBlock** функция проверяет, что указанный блок памяти находится в локальной куче и имеет допустимый идентификатор типа блока. Эту функцию можно также использовать для получения порядкового номера распределения объекта, а также имени или номера строки исходного файла, содержащего исходный запрос на выделение блока памяти. Передача отличных**NULL** значений в параметре *requestNumber*, *filename*, или *linenumber* причины параметры **_ CrtIsMemoryBlock** присваивать этим параметрам со значениями в заголовка отладки блока памяти, при обнаружении блока в локальной куче. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtIsMemoryBlock** удаляются во время предварительной обработки.

Если **_CrtIsMemoryBlock** завершается ошибкой, возвращается **FALSE** и выходным параметрам присваиваются значения по умолчанию: *requestNumber* и **lineNumber**  присваиваются значения 0 и *filename* присваивается **NULL**.

Так как эта функция возвращает значение **TRUE** или **FALSE**, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Приведенный ниже пример вызывает сбой утверждения, если указанный адрес находится не в локальной куче.

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Дополнительные сведения о том, как **_CrtIsMemoryBlock** можно использовать с другими функциями и макросами отладки, см. в разделе [макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

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

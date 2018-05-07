---
title: _CrtIsMemoryBlock | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dee3e30e5bde5a3bed67d975c96b00568306f926
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

*Устойчивость данных пользователя*<br/>
Указатель на начало блока памяти, требующего проверки.

*size*<br/>
Размер указанного блока в байтах.

*requestNumber*<br/>
Указатель на номер выделения блока или **NULL**.

*filename*<br/>
Указатель на имя исходного файла, который запросил блока или **NULL**.

*linenumber*<br/>
Указатель на номер строки в исходном файле или **NULL**.

## <a name="return-value"></a>Возвращаемое значение

**_CrtIsMemoryBlock** возвращает **TRUE** Если указанный блок памяти находится в локальной куче и имеет допустимый отладочной кучи блок идентификатор типа; в противном случае функция возвращает значение **FALSE**.

## <a name="remarks"></a>Примечания

**_CrtIsMemoryBlock** функция проверяет, находится ли указанный блок памяти в локальной куче приложения, содержащий идентификатор типа допустимым блоком. Эту функцию можно также использовать для получения порядкового номера распределения объекта, а также имени или номера строки исходного файла, содержащего исходный запрос на выделение блока памяти. Передача значений, отличных от NULL для *requestNumber*, *filename*, или *linenumber* причины параметры **_CrtIsMemoryBlock** для установки Эти параметры к значениям в блок памяти отладки заголовок, при обнаружении блока в локальной куче. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtIsMemoryBlock** удаляются на этапе предварительной обработки.

Если **_CrtIsMemoryBlock** завершается ошибкой, возвращается **FALSE** и выходные параметры инициализируются значениями по умолчанию: *requestNumber* и **lineNumber**  равны 0 и *filename* равно **NULL**.

Так как эта функция возвращает значение **TRUE** или **FALSE**, ее можно передать в один из макросов [_ASSERT](assert-asserte-assert-expr-macros.md) для создания простого механизма обработки ошибок отладки. Приведенный ниже пример вызывает сбой утверждения, если указанный адрес находится не в локальной куче.

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Дополнительные сведения о том, как **_CrtIsMemoryBlock** можно использовать с другими функциями и макросами отладки см. в разделе [макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

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

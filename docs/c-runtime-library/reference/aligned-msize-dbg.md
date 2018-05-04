---
title: _aligned_msize_dbg | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c16fd1292f78c8c3f6b3133050e27046fb003343
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg

Возвращает размер блока памяти, выделенного в куче (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C
size_t _aligned_msize_dbg(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель на блок памяти.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

Возвращает размер (в байтах) как целое число без знака.

## <a name="remarks"></a>Примечания

*Выравнивание* и *смещение* значения должны совпадать с именем значения, переданные функции, выделившей блок.

**_aligned_msize_dbg** является отладочной версией [_aligned_msize](aligned-msize.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_aligned_msize_dbg** сокращается до вызова **_aligned_msize**. Оба **_aligned_msize** и **_aligned_msize_dbg** вычислить размер блока памяти в основной куче, но **_aligned_msize_dbg** добавляет функцию отладки: он включает Возвращаемый размер блокировать буферов по обеим сторонам пользовательского участка памяти.

Эта функция проверяет свои параметры. Если *memblock* является пустым указателем или *выравнивание* не является степенью 2, **_msize** вызывает обработчик недопустимого параметра, как описано в [проверка параметров ](../../c-runtime-library/parameter-validation.md). Если ошибка будет обработана, функция устанавливает **errno** для **EINVAL** и возвращает значение -1.

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>

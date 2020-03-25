---
title: _aligned_free
ms.date: 11/04/2016
api_name:
- _aligned_free
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- aligned_free
- _aligned_free
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
ms.openlocfilehash: 0fa28be550050a7eec2a515cfb47d98fb26591d0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170973"
---
# <a name="_aligned_free"></a>_aligned_free

Освобождает блок памяти, который был выделен с помощью функции [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Синтаксис

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель на блок памяти, возвращенный в функцию `_aligned_malloc` или `_aligned_offset_malloc`.

## <a name="remarks"></a>Remarks

**_aligned_free** помечается как `__declspec(noalias)`, то есть гарантируется, что функция не будет изменять глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).

Эта функция в отличие от других функций CRT _aligned не проверяет свой параметр. Если *мемблокк* является пустым указателем, эта функция просто не выполняет никаких действий. Она не влияет на `errno` и не вызывает обработчик недопустимых параметров. Если в функции возникает ошибка, связанная с тем, что предварительно для выделения блоков памяти не использовались функции _aligned либо в результате непредвиденного сбоя возникла ошибка распределения памяти, функция создает отчет отладки, используя [макросы _RPT, _RPTF, _RPTW, _RPTFW](rpt-rptf-rptw-rptfw-macros.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>См. также раздел

[Выравнивание данных](../../c-runtime-library/data-alignment.md)

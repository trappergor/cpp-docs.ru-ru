---
title: _aligned_free | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_free
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- aligned_free
- _aligned_free
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e18c02909c247af4066033fc3e3633db74327f55
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102646"
---
# <a name="alignedfree"></a>_aligned_free

Освобождает блок памяти, который был выделен с помощью функции [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Синтаксис

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Параметры

*memblock*  
Указатель на блок памяти, возвращенный в функцию `_aligned_malloc` или `_aligned_offset_malloc`.

## <a name="remarks"></a>Примечания

**_aligned_free** помечен `__declspec(noalias)`, это означает, что функция гарантированно не изменит глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).

Эта функция в отличие от других функций CRT _aligned не проверяет свой параметр. Если *memblock* является указателем NULL, эта функция просто не выполняет никаких действий. Она не влияет на `errno` и не вызывает обработчик недопустимых параметров. Если в функции возникает ошибка, связанная с тем, что предварительно для выделения блоков памяти не использовались функции _aligned либо в результате непредвиденного сбоя возникла ошибка распределения памяти, функция создает отчет отладки, используя [макросы _RPT, _RPTF, _RPTW, _RPTFW](rpt-rptf-rptw-rptfw-macros.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>См. также

[Выравнивание данных](../../c-runtime-library/data-alignment.md)  
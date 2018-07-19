---
title: _aligned_free_dbg | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88c7eb281ecc7a7175614c5c72c54c7267cf55e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393463"
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg

Освобождает блок памяти, который был выделен с помощью [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md) (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>Параметры

*memblock* указатель на блок памяти, возвращенный в [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md) функции.

## <a name="remarks"></a>Примечания

**_Aligned_free_dbg** функция является отладочной версией [_aligned_free](aligned-free.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_aligned_free_dbg** сокращается до вызова **_aligned_free**. Оба **_aligned_free** и **_aligned_free_dbg** освобождения блока памяти в основной куче, но **_aligned_free_dbg** включает возможность отладки: возможность хранить освободившиеся блоки в связанном списке кучи для моделирования условий недостатка памяти.

**_aligned_free_dbg** выполняет проверку действительности для всех указанных файлов и расположений блоков перед выполнением операции освобождения. Приложение не ожидает предоставления этих сведений. Когда освобождается блок памяти, диспетчер отладочной кучи автоматически проверяет целостность буферов по обеим сторонам пользовательской части и выдает отчет об ошибке в случае их перезаписи. Если **_CRTDBG_DELAY_FREE_MEM_DF** битовое поле [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) флаг установлен, освободившийся блок заполняется значением 0xDD, назначенный **_FREE_BLOCK** блокировку типа, и хранятся в связанном списке кучи блоков памяти.

Если произошла ошибка при освобождении памяти, **errno** задаются сведения из операционной системы о характере сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>

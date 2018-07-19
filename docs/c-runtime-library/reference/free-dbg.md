---
title: _free_dbg | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa485eea6f0ffda05b0ef33a808d5ec837255514
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400048"
---
# <a name="freedbg"></a>_free_dbg

Освобождает блок памяти в куче (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>Параметры

*userData* указатель на выделенный блок памяти, освобождаемой.

*blockType* тип выделенного блока памяти для освобождения: **_CLIENT_BLOCK**, **_NORMAL_BLOCK**, или **_IGNORE_BLOCK**.

## <a name="remarks"></a>Примечания

**_Free_dbg** функция является отладочной версией [свободного](free.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_free_dbg** сокращается до вызова **свободного**. Оба **свободного** и **_free_dbg** освобождения блока памяти в основной куче, но **_free_dbg** включает две функции отладки: возможность хранить освободившиеся блоки в куче связанный список для эмуляции условий нехватки памяти и параметр типа блока для освобождения определенных типов выделения памяти.

**_free_dbg** выполняет проверку действительности для всех указанных файлов и расположений блоков перед выполнением операции освобождения. Приложение не ожидает предоставления этих сведений. Когда освобождается блок памяти, диспетчер отладочной кучи автоматически проверяет целостность буферов по обеим сторонам пользовательской части и выдает отчет об ошибке в случае их перезаписи. Если **_CRTDBG_DELAY_FREE_MEM_DF** битовое поле [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) флаг установлен, освободившийся блок заполняется значением 0xDD, назначенный **_FREE_BLOCK** блокировку типа, и хранятся в связанном списке кучи блоков памяти.

Если произошла ошибка при освобождении памяти, **errno** задаются сведения из операционной системы о характере сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Пример использования **_free_dbg**, в разделе [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>

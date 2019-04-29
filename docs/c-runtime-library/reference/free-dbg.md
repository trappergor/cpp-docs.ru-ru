---
title: _free_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 5a0024101e4f5a74f1573b271d444b27738db8e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287867"
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

*userData*<br/>
Указатель на выделенный блок памяти, который требуется освободить.

*blockType*<br/>
Тип блока памяти, освобождаемой: **_CLIENT_BLOCK**, **_NORMAL_BLOCK**, или **_IGNORE_BLOCK**.

## <a name="remarks"></a>Примечания

**_Free_dbg** функция — это отладочная версия [бесплатный](free.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_free_dbg** сокращается до вызова **бесплатный**. Оба **бесплатный** и **_free_dbg** освобождают блок памяти в основной куче, но **_free_dbg** включает две возможности отладки: возможность хранить освободившиеся блоки в куче связанном списке для моделирования условий недостатка памяти и параметр типа блока для освобождения конкретных типов выделения.

**_free_dbg** выполняет проверку допустимости для всех указанных файлов и расположений блоков перед выполнением операции освобождения. Приложение не ожидает предоставления этих сведений. Когда освобождается блок памяти, диспетчер отладочной кучи автоматически проверяет целостность буферов по обеим сторонам пользовательской части и выдает отчет об ошибке в случае их перезаписи. Если **_CRTDBG_DELAY_FREE_MEM_DF** битовое поле [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) флаг установлен, освободившийся блок заполняется значением 0xDD, назначенный **_FREE_BLOCK** блокировку типа, и хранится в кучи в связанном списке блоков памяти.

Если произошла ошибка при освобождении памяти, **errno** задается с помощью сведения из операционной системы от характера сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Пример использования **_free_dbg**, см. в разделе [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>

---
title: fclose, _fcloseall
ms.date: 11/04/2016
api_name:
- fclose
- _fcloseall
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 215925fb16f5d51e481ae92cbb45b0270bd5ebd4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941502"
---
# <a name="fclose-_fcloseall"></a>fclose, _fcloseall

Закрывает поток (**фклосе**) или закрывает все открытые потоки ( **_fcloseall**).

## <a name="syntax"></a>Синтаксис

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Параметры

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**фклосе** возвращает 0, если поток успешно закрыт. **_fcloseall** возвращает общее число закрытых потоков. Обе функции возвращают **EOF** , чтобы указать ошибку.

## <a name="remarks"></a>Примечания

Функция **фклосе** закрывает *поток*. Если *Stream* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено , фклосе **устанавливает значение** переводится в **еинвал** и возвращает **EOF**. Рекомендуется всегда проверять указатель *потока* перед вызовом этой функции.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Функция **_fcloseall** закрывает все открытые потоки, за исключением **stdin**, **stdout**, **stderr** (и, в MS-DOS, **_stdaux** и **_stdprn**). Он также закрывает и удаляет временные файлы, созданные **tmpfile**. При использовании обеих функций все буферы, связанные с потоком, перед закрытием сбрасываются. При закрытии потока выделенные системой буферы освобождаются. Буферы, назначенные пользователем с помощью **setbuf** и **setvbuf** , не освобождаются автоматически.

**Примечание.** Когда эти функции используются для закрытия потока, базовый дескриптор файла и дескриптор файла операционной системы (или сокет) закрываются, а также поток. Таким образом, если файл был первоначально открыт как дескриптор файла или дескриптор файла и закрывается с помощью **фклосе**, не вызывайте **_close** , чтобы закрыть дескриптор файла. не вызывайте функцию Win32 в **CloseHandle** для закрытия маркера файла.

**фклосе** и **_fcloseall** включают код для защиты от помех от других потоков. Сведения о неблокирующей версии **фклосе**см. в разделе **_fclose_nolock**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fopen](fopen-wfopen.md).

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>

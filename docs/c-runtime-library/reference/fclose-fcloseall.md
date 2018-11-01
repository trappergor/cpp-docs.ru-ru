---
title: fclose, _fcloseall
ms.date: 11/04/2016
apiname:
- fclose
- _fcloseall
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 4713ffb7ecdf8da73e5f949bbef7be124dfaf28a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536517"
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall

Закрывает поток (**fclose**) или закрывает все открытые потоки (**_fcloseall**).

## <a name="syntax"></a>Синтаксис

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Параметры

*поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fclose** возвращает 0, если поток был успешно закрыт. **_fcloseall** возвращает общее количество закрытых потоков. Обе функции возвращают **EOF** для указания ошибки.

## <a name="remarks"></a>Примечания

**Fclose** функцию закрытия *поток*. Если *поток* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **fclose** задает **errno** для **EINVAL** и возвращает **EOF**. Рекомендуется *поток* всегда проверяйте указатель перед вызовом этой функции.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**_Fcloseall** функция закрывает все открытые потоки, за исключением **stdin**, **stdout**, **stderr** (а в MS-DOS, **_stdaux**  и **_stdprn**). Она также закрывает и удаляет все временные файлы, созданные **tmpfile**. При использовании обеих функций все буферы, связанные с потоком, перед закрытием сбрасываются. При закрытии потока выделенные системой буферы освобождаются. Буферы, назначенные пользователем с помощью **setbuf** и **setvbuf** , автоматически не освобождаются.

**Примечание.** При использовании этих функций для закрытия потока вместе с ним закрываются также базовый дескриптор файла и обработчик (или сокет) файла операционной системы. Таким образом, если файл был открыт как обработчик или дескриптор файла и закрыт с **fclose**, не следует вызывать функцию **_close** чтобы закрыть дескриптор файла; не следует вызывать функцию Win32  **CloseHandle** закрыть дескриптор файла.

**fclose** и **_fcloseall** включают код для защиты от помех от других потоков. Для неблокирующей версии из **fclose**, см. в разделе **_fclose_nolock**.

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

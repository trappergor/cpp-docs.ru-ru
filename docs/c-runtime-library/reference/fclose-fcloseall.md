---
title: fclose, _fcloseall
ms.date: 4/2/2020
api_name:
- fclose
- _fcloseall
- _o__fcloseall
- _o_fclose
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b2ee14c5fc8bb47cc2652443c0263bd14147c90d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347494"
---
# <a name="fclose-_fcloseall"></a>fclose, _fcloseall

Закрывает поток **(притефиза)** или закрывает все открытые потоки **(_fcloseall).**

## <a name="syntax"></a>Синтаксис

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fclose** возвращает 0, если поток успешно закрыт. **_fcloseall** возвращает общее количество закрытых потоков. Обе функции возвращают **EOF** для указания ошибки.

## <a name="remarks"></a>Remarks

Функция **fclose** закрывает *поток.* Если *поток* **NULL,** вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **fclose** устанавливает **errno** к **EINVAL** и возвращает **EOF**. Рекомендуется всегда проверять указатель *потока* перед вызовом этой функции.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Функция **_fcloseall** закрывает все открытые потоки, кроме **stdin,** **stdout,** **stderr** (и, в MS-DOS, **_stdaux** и **_stdprn).** Он также закрывает и удаляет любые временные файлы, созданные **tmpfile.** При использовании обеих функций все буферы, связанные с потоком, перед закрытием сбрасываются. При закрытии потока выделенные системой буферы освобождаются. Буферы, назначенные пользователем с **setbuf** и **setvbuf,** автоматически не освобождаются.

**Примечание.** При использовании этих функций для закрытия потока вместе с ним закрываются также базовый дескриптор файла и обработчик (или сокет) файла операционной системы. Таким образом, если файл был первоначально открыт в качестве ручки файла или дескриптора файла и закрыт **с помощью огню,** не звоните **_close,** чтобы закрыть дескриптор файла; не вызывайте функцию Win32 **CloseHandle,** чтобы закрыть ручку файла.

**fclose** **_fcloseall** включают код для защиты от помех от других потоков. Для незапирающей версии **флокса**см. **_fclose_nolock**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fopen](fopen-wfopen.md).

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>

---
title: fclose, _fcloseall | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71b98a239cd1a6504611bf436533e7b5fbe1302c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall

Закрывает поток (**fclose**) или закрытие всех открытых потоков (**_fcloseall**).

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

**fclose** возвращает 0, если поток закрыт успешно. **_fcloseall** возвращает общее количество потоков, которые закрыты. Обе функции возвращают **EOF** для указания ошибки.

## <a name="remarks"></a>Примечания

**Fclose** функцию закрытия *поток*. Если *поток* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **fclose** задает **errno** для **EINVAL** и возвращает **EOF**. Рекомендуется *поток* указатель всегда проверяться перед вызовом этой функции.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**_Fcloseall** функция закрытие всех открытых потоков, кроме **stdin**, **stdout**, **stderr** (и в MS-DOS **_stdaux**  и **_stdprn**). Также закрывает и удаляет все временные файлы, созданные **tmpfile**. При использовании обеих функций все буферы, связанные с потоком, перед закрытием сбрасываются. При закрытии потока выделенные системой буферы освобождаются. Буферы, назначенный пользователем с помощью **setbuf** и **setvbuf** не освобождается автоматически.

**Примечание.** При использовании этих функций для закрытия потока вместе с ним закрываются также базовый дескриптор файла и обработчик (или сокет) файла операционной системы. Таким образом, если файл был открыт в формате обработки или дескриптор файла и закрывается с **fclose**, также не выполнения вызова **_close** для закрыть дескриптор файла; нужно вызывать функцию Win32  **CloseHandle** закрыть дескриптор файла.

**fclose** и **_fcloseall** включить код для защиты от вмешательства других потоков. Для неблокирующую версию из **fclose**, в разделе **_fclose_nolock**.

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

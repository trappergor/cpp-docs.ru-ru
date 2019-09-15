---
title: _ungetc_nolock, _ungetwc_nolock
ms.date: 11/04/2016
api_name:
- _ungetwc_nolock
- _ungetc_nolock
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
- _ungettc_nolock
- ungetwc_nolock
- ungetc_nolock
- _ungetc_nolock
- _ungetwc_nolock
helpviewer_keywords:
- _ungettc_nolock function
- _ungetwc_nolock function
- characters, pushing back onto stream
- _ungetc_nolock function
- ungetwc_nolock function
- ungettc_nolock function
- ungetc_nolock function
ms.assetid: aa02d5c2-1be1-46d2-a8c4-b61269e9d465
ms.openlocfilehash: 4228a573a0277c9bacc8beea81cbff6a70e3fe83
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945929"
---
# <a name="_ungetc_nolock-_ungetwc_nolock"></a>_ungetc_nolock, _ungetwc_nolock

Помещает символ обратно в поток.

## <a name="syntax"></a>Синтаксис

```C
int _ungetc_nolock(
   int c,
   FILE *stream
);
wint_t _ungetwc_nolock(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется поместить обратно.

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха каждая из этих функций Возвращает символьный аргумент *c*. Если *c* не удается вернуть обратно или если ни один символ не был считан, входной поток не изменяется, а **_ungetc_nolock** возвращает **EOF**; **_ungetwc_nolock** возвращает **WEOF**. Если *Stream* имеет **значение NULL**, возвращается **EOF** или **WEOF** , **а параметру** "переводится" значение **еинвал**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Эти функции являются версиями **ungetc** и **ungetwc**без блокировки. Версии с суффиксом **_nolock** идентичны за исключением того, что они не защищены от помех со стороны других потоков. Они могут выполняться быстрее, так как не создают дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc_nolock**|**_ungetc_nolock**|**_ungetc_nolock**|**_ungetwc_nolock**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ungetc_nolock**|\<stdio.h>|
|**_ungetwc_nolock**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>

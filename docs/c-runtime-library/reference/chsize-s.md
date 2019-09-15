---
title: _chsize_s
ms.date: 11/04/2016
api_name:
- _chsize_s
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
- chsize_s
- _chsize_s
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
ms.openlocfilehash: 7250f0b570ae9a4b2478bad09ee7b0044068d972
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939181"
---
# <a name="_chsize_s"></a>_chsize_s

Изменяет размер файла. Это версия функции [_chsize](chsize.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор файла, ссылающийся на открытый файл.

*size*<br/>
Новая длина файла в байтах.

## <a name="return-value"></a>Возвращаемое значение

**_chsize_s** возвращает значение 0, если размер файла успешно изменен. Ненулевое возвращаемое значение указывает на ошибку: возвращаемое значение равно **еакцес** , если указанный файл заблокирован для доступа, **значение EBADF** , если указанный файл доступен только для чтения или дескриптор недействителен, **еноспк** , если на устройстве не осталось свободного места, или  **ЕИНВАЛ** , если размер меньше нуля. для свойства "прежний **" задано** одно и то же значение.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_chsize_s** расширяет или усекает файл, связанный с *демоном* , до длины, указанной в параметре *size*. Файл должен быть открыт в режиме, позволяющем выполнять запись. Если файл доступен для расширения, к нему добавляются нули ('\0'). Если файл усекается, все данные в конце сокращенного файла усекаются до длины исходного файла.

**_chsize_s** принимает 64-разрядное целое число в качестве размера файла и, следовательно, может работать с размерами файлов, превышающими 4 ГБ. **_chsize** имеет ограничение в 32-разрядных размерах файлов.

Эта функция проверяет свои параметры. Если *демон* не является допустимым дескриптором файла или его размер меньше нуля, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>

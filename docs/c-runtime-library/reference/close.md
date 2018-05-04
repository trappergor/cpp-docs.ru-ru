---
title: _close | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _close
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
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eabf084d2e4dd7e280c0ff730d1ec34d86f1ed98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="close"></a>_close

Закрывает файл.

## <a name="syntax"></a>Синтаксис

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор файла, ссылающийся на открытый файл.

## <a name="return-value"></a>Возвращаемое значение

**_Закрыть** возвращает 0, если файл был успешно закрыт. Возвращаемое значение-1 указывает на ошибку.

## <a name="remarks"></a>Примечания

**_Close** функция закрывает файл, связанный с *fd*.

Дескриптор файла и соответствующий обработчик файлов операционной системы закрываются. Таким образом, нет необходимости вызывать **CloseHandle** Если файл был открыт с помощью функции Win32 **CreateFile** и преобразуется в файле дескриптора с помощью **_open_osfhandle**.

Эта функция проверяет свои параметры. Если *fd* имеет недопустимый идентификатор файла, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и **errno** равно **EBADF**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_open](open-wopen.md).

## <a name="see-also"></a>См. также

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>

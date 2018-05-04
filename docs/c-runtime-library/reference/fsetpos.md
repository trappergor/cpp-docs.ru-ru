---
title: fsetpos | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fsetpos
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
- fsetpos
dev_langs:
- C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c381cf478a97d47efe10c68096fffe3d9fd8efdf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fsetpos"></a>fsetpos

Задает индикатор позиции в потоке.

## <a name="syntax"></a>Синтаксис

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

*POS*<br/>
Хранилище индикатора позиции.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **fsetpos** возвращает 0. В случае неудачи, функция возвращает ненулевое значение и задает **errno** к одному из следующих манифеста констант (определенных в ERRNO. H): **EBADF**, это означает, что файл не доступен, или объект, *поток* указывает не является допустимым файлом структурой; или **EINVAL**, означающее недопустимое значение *поток* или *pos* был передан. Если передан недопустимый параметр, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Fsetpos** функция задает для индикатора позиции файла *поток* значению *pos*, который получается в предыдущем вызове **fgetpos**от *поток*. Функция очищает индикатор end of file и отменяет последствия [ungetc](ungetc-ungetwc.md) на *поток*. После вызова метода **fsetpos**, следующая операция *поток* может быть либо входного или выходного.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fgetpos](fgetpos.md).

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>

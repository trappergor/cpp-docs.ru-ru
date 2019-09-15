---
title: _umask_s
ms.date: 11/04/2016
api_name:
- _umask_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unmask_s
- _umask_s
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
ms.openlocfilehash: 21d9ba194f85e40c3c5a4d67d16ebca9721f68f8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945988"
---
# <a name="_umask_s"></a>_umask_s

Задает маску разрешений файла по умолчанию. Версия функции [_umask](umask.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _umask_s(
   int mode,
   int * pOldMode
);
```

### <a name="parameters"></a>Параметры

*mode*<br/>
Параметр разрешения по умолчанию.

*полдмоде*<br/>
Прежнее значение параметра разрешения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает код ошибки, если *режим* не указывает допустимый режим, или указатель *Полдмоде* имеет **значение NULL**.

### <a name="error-conditions"></a>Условия ошибок

|*mode*|*полдмоде*|Возвращаемое значение|Содержимое *полдмоде*|
|------------|----------------|----------------------|--------------------------------|
|Любое действие|**NULL**|**EINVAL**|не изменено|
|недопустимый режим|Любое действие|**EINVAL**|не изменено|

Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_umask_s** возвращает **еинвал** и **задает** для **еинвал**.

## <a name="remarks"></a>Примечания

Функция **_umask_s** устанавливает в качестве маски разрешений файла текущего процесса режим, заданный *режимом*. Маска разрешений файла изменяет настройки разрешений для новых файлов, созданных с помощью **_creat**, **_open**или **_sopen**. Если бит в битовой маске равен 1, соответствующий бит в запрошенном значении разрешения имеет значение 0 (запрещено). Если бит в битовой маске равен 0, соответствующий бит остается без изменений. Параметр разрешения для нового файла не устанавливается до тех пор, пока файл не будет закрыт в первый раз.

Целочисленное выражение *пмоде* содержит одну или обе следующие константы манифеста, определенные в сис\стат. Высоты

|*пмоде*||
|-|-|
|**_S_IWRITE**|Разрешена запись.|
|**_S_IREAD**|Разрешено чтение.|
|**_S_IREAD** \| **_S_IWRITE**|Разрешены чтение и запись.|

Если заданы обе константы, они соединяются с оператором побитового или **|** (). Если аргумент *mode* имеет значение **_S_IREAD**, чтение запрещено (файл доступен только для записи). Если аргумент *mode* имеет значение **_S_IWRITE**, запись не допускается (файл доступен только для чтения). Например, если в маске установлен бит записи, все новые файлы будут доступны только для чтения. Обратите внимание, что в операционных системах MS-DOS и Windows все файлы доступны для чтения; невозможно предоставить разрешение только на запись. Поэтому Установка бита чтения с **_umask_s** не влияет на режимы файла.

Если *пмоде* не является сочетанием одной из констант манифеста или включает другой набор констант, функция будет просто игнорировать их.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_umask_s**|\<io.h> и \<sys/stat.h> и \<sys/types.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_umask_s.c
/* This program uses _umask_s to set
* the file-permission mask so that all future
* files will be created as read-only files.
* It also displays the old mask.
*/

#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask, err;

   /* Create read-only files: */
   err = _umask_s( _S_IWRITE, &oldmask );
   if (err)
   {
      printf("Error setting the umask.\n");
      exit(1);
   }
   printf( "Oldmask = 0x%.4x\n", oldmask );
}
```

```Output
Oldmask = 0x0000
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_umask](umask.md)<br/>

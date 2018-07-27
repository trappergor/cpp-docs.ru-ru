---
title: _umask_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _umask_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d45cb3ded6fd2c3d7a380069a7d7f3fd79619810
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414484"
---
# <a name="umasks"></a>_umask_s

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

*pOldMode*<br/>
Прежнее значение параметра разрешения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает код ошибки, если *режим* не указан недопустимый режим или *pOldMode* указатель **NULL**.

### <a name="error-conditions"></a>Условия ошибок

|*mode*|*pOldMode*|Возвращаемое значение|Содержимое *pOldMode*|
|------------|----------------|----------------------|--------------------------------|
|any|**NULL**|**EINVAL**|не изменено|
|недопустимый режим|any|**EINVAL**|не изменено|

Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_umask_s** возвращает **EINVAL** и задает **errno** для **EINVAL**.

## <a name="remarks"></a>Примечания

**_Umask_s** , функция задает маску разрешений файла текущего процесса значение режима, указанного по *режим*. Маску разрешений файла изменяет разрешения для новых файлов, созданных **_creat**, **_open**, или **_sopen**. Если бит в битовой маске равен 1, соответствующий бит в запрошенном значении разрешения имеет значение 0 (запрещено). Если бит в битовой маске равен 0, соответствующий бит остается без изменений. Параметр разрешения для нового файла не устанавливается до тех пор, пока файл не будет закрыт в первый раз.

Целочисленное выражение *pmode* содержит одно или оба из следующих констант манифеста, определенных в SYS\STAT. H:

|*pmode*||
|-|-|
|**_S_IWRITE**|Разрешена запись.|
|**_S_IREAD**|Разрешено чтение.|
|**_S_IREAD** \| **_S_IWRITE**|Разрешены чтение и запись.|

Если заданы обе константы, они объединяются с помощью оператора побитового или ( **|** ). Если *режим* аргумент **_S_IREAD**, чтение запрещено (файл доступен только для записи). Если *режим* аргумент **_S_IWRITE**, записи не разрешен (файл доступен только для чтения). Например, если в маске установлен бит записи, все новые файлы будут доступны только для чтения. Обратите внимание, что в операционных системах MS-DOS и Windows все файлы доступны для чтения; невозможно предоставить разрешение только на запись. Таким образом, задание чтения bit **_umask_s** не влияет на режимы файла.

Если *pmode* не является сочетанием одного из констант манифеста или включает дополнительный набор констант, функция будет игнорировать их.

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

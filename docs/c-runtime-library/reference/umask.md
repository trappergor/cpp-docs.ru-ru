---
title: _umask | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _umask
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
- _umask
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce3053bfb19cc81dff15d41d1b5bc6d405da619f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412620"
---
# <a name="umask"></a>_umask

Задает маску разрешений файла по умолчанию. Существует более безопасная версия этой функции, см. раздел [_umask_s](umask-s.md).

## <a name="syntax"></a>Синтаксис

```C
int _umask( int pmode );
```

### <a name="parameters"></a>Параметры

*pmode*<br/>
Параметр разрешения по умолчанию.

## <a name="return-value"></a>Возвращаемое значение

**_umask** возвращает предыдущее значение *pmode*. Ошибка не возвращается.

## <a name="remarks"></a>Примечания

**_Umask** , функция задает маску разрешений файла текущего процесса значение режима, указанного по *pmode*. Маску разрешений файла изменяет разрешения для новых файлов, созданных **_creat**, **_open**, или **_sopen**. Если бит в битовой маске равен 1, соответствующий бит в запрошенном значении разрешения имеет значение 0 (запрещено). Если бит в битовой маске равен 0, соответствующий бит остается без изменений. Параметр разрешения для нового файла не устанавливается до тех пор, пока файл не будет закрыт в первый раз.

Целочисленное выражение *pmode* содержит одно или оба из следующих констант манифеста, определенных в SYS\STAT. H:

|*pmode*||
|-|-|
**_S_IWRITE**|Разрешена запись.
**_S_IREAD**|Разрешено чтение.
**_S_IREAD** \| **_S_IWRITE**|Разрешены чтение и запись.

Если заданы обе константы, они объединяются с помощью оператора побитового или ( **|** ). Если *pmode* аргумент **_S_IREAD**, чтение запрещено (файл доступен только для записи). Если *pmode* аргумент **_S_IWRITE**, записи не разрешен (файл доступен только для чтения). Например, если в маске установлен бит записи, все новые файлы будут доступны только для чтения. Обратите внимание, что в операционных системах MS-DOS и Windows все файлы доступны для чтения; невозможно предоставить разрешение только на запись. Таким образом, задание чтения bit **_umask** не влияет на режимы файла.

Если *pmode* не является сочетанием одного из констант манифеста или включает дополнительный набор констант, функция будет игнорировать их.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_umask**|\<io.h>, \<sys/stat.h>, \<sys/types.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_umask.c
// compile with: /W3
// This program uses _umask to set
// the file-permission mask so that all future
// files will be created as read-only files.
// It also displays the old mask.
#include <sys/stat.h>
#include <sys/types.h>
#include <io.h>
#include <stdio.h>

int main( void )
{
   int oldmask;

   /* Create read-only files: */
   oldmask = _umask( _S_IWRITE ); // C4996
   // Note: _umask is deprecated; consider using _umask_s instead
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

---
title: _umask
ms.date: 4/2/2020
api_name:
- _umask
- _o__umask
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _umask
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
ms.openlocfilehash: b451f979f2925a31f5baaac52351c5d2c0a76da0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362022"
---
# <a name="_umask"></a>_umask

Задает маску разрешений файла по умолчанию. Существует более безопасная версия этой функции, см. раздел [_umask_s](umask-s.md).

## <a name="syntax"></a>Синтаксис

```C
int _umask( int pmode );
```

### <a name="parameters"></a>Параметры

*pmode*<br/>
Параметр разрешения по умолчанию.

## <a name="return-value"></a>Возвращаемое значение

**_umask** возвращает прежнее значение *pmode*. Ошибка не возвращается.

## <a name="remarks"></a>Remarks

Функция **_umask** устанавливает маску разрешения файла текущего процесса в режим, указанный *pmode.* Маска разрешения файлов изменяет настройку разрешения новых файлов, созданных **_creat,** **_open**или **_sopen.** Если бит в битовой маске равен 1, соответствующий бит в запрошенном значении разрешения имеет значение 0 (запрещено). Если бит в битовой маске равен 0, соответствующий бит остается без изменений. Параметр разрешения для нового файла не устанавливается до тех пор, пока файл не будет закрыт в первый раз.

В истеже *выражении pmode* содержится одна или обе следующие константы манифеста, определенные в SYS-STAT. H:

|*pmode*| |
|-|-|
| **_S_IWRITE** | Разрешена запись. |
| **_S_IREAD** | Разрешено чтение. |
| **_S_IREAD** **&#124; _S_IWRITE** | Разрешены чтение и запись. |

Когда обе константы даны, они соединены с bitwise-OR оператором **(&#124;).** Если *аргумент pmode* **_S_IREAD,** чтение не допускается (файл только для записи). Если аргумент *pmode* **является _S_IWRITE,** написание не допускается (файл читается только читать). Например, если в маске установлен бит записи, все новые файлы будут доступны только для чтения. Обратите внимание, что в операционных системах MS-DOS и Windows все файлы доступны для чтения; невозможно предоставить разрешение только на запись. Таким образом, установка чтения бит с **_umask** не влияет на режимы файла.

Если *pmode* не является сочетанием одной из явных констант или включает в себя альтернативный набор констант, функция будет просто игнорировать их.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_umask**|\<io.h>, \<sys/stat.h>, \<sys/types.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>

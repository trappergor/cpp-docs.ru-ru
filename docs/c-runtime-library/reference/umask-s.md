---
title: _umask_s
ms.date: 4/2/2020
api_name:
- _umask_s
- _o__umask_s
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
ms.openlocfilehash: d590910d5f5092a78ad64c8f9ef0aa259211e226
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362182"
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

*Режим*<br/>
Параметр разрешения по умолчанию.

*pOldMode*<br/>
Прежнее значение параметра разрешения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает код ошибки, если *режим* не указывает допустимый режим или указатель *pOldMode* **null.**

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*Режим*|*pOldMode*|Возвращаемое значение|Содержимое *pOldMode*|
|------------|----------------|----------------------|--------------------------------|
|any|**Null**|**EINVAL**|не изменено|
|недопустимый режим|any|**EINVAL**|не изменено|

Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, **_umask_s** возвращает **EINVAL** и устанавливает **errno** в **EINVAL**.

## <a name="remarks"></a>Remarks

Функция **_umask_s** устанавливает маску разрешения файла текущего процесса в режим, указанный *режимом.* Маска разрешения файлов изменяет настройку разрешения новых файлов, созданных **_creat,** **_open**или **_sopen.** Если бит в битовой маске равен 1, соответствующий бит в запрошенном значении разрешения имеет значение 0 (запрещено). Если бит в битовой маске равен 0, соответствующий бит остается без изменений. Параметр разрешения для нового файла не устанавливается до тех пор, пока файл не будет закрыт в первый раз.

В истеже *выражении pmode* содержится одна или обе следующие константы манифеста, определенные в SYS-STAT. H:

|*pmode*||
|-|-|
|**_S_IWRITE**|Разрешена запись.|
|**_S_IREAD**|Разрешено чтение.|
|**_S_IREAD** \| **_S_IWRITE**|Разрешены чтение и запись.|

Когда обе константы даны, они соединены с **|** bitwise-OR оператором ( ). Если аргумент *режима* **_S_IREAD,** чтение не допускается (файл является только записью). Если аргумент *режима* **_S_IWRITE,** написание не допускается (файл читается только читать). Например, если в маске установлен бит записи, все новые файлы будут доступны только для чтения. Обратите внимание, что в операционных системах MS-DOS и Windows все файлы доступны для чтения; невозможно предоставить разрешение только на запись. Таким образом, установка чтения бит с **_umask_s** не влияет на режимы файла.

Если *pmode* не является сочетанием одной из явных констант или включает в себя альтернативный набор констант, функция будет просто игнорировать их.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_umask_s**|\<io.h> и \<sys/stat.h> и \<sys/types.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_umask](umask.md)<br/>

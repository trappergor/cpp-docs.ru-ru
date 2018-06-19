---
title: _creat _wcreat | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _creat
- _wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6b987faa30439f0f374838fe7fcd4d942b8cc7
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451853"
---
# <a name="creat-wcreat"></a>Функция _creat, _wcreat

Создание нового файла. **_creat** и **_wcreat** являются устаревшими; используйте [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) вместо него.

## <a name="syntax"></a>Синтаксис

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Имя нового файла.

*pmode*<br/>
Настройка разрешений.

## <a name="return-value"></a>Возвращаемое значение

Эти функции при успешном завершении возвращают дескриптор созданного файла. В противном случае функции возвращают значение -1 и задайте **errno** как показано в следующей таблице.

|**errno** параметр|Описание|
|---------------------|-----------------|
|**EACCES**|*Имя файла* указывает существующий файл только для чтения или указывает каталог вместо файла.|
|**EMFILE**|Больше нет доступных дескрипторов файлов.|
|**ENOENT**|Не удалось найти указанный файл.|

Если *filename* — **NULL**, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают -1.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Creat** функция создает новый файл или открывает и обрезает существующий. **_wcreat** — это двухбайтовая версия **_creat**; *filename* аргумент **_wcreat** представляет собой строку расширенных символов. **_wcreat** и **_creat** ведут себя идентично.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

Если файл, указанный параметром *filename* не существует, новый файл создается с заданными настройками разрешений и открыт для записи. Если файл уже существует и его настройки разрешений допускают запись, **_creat** обрезает файл до длины 0, уничтожая предыдущее содержимое и открывает его для записи. Настройка разрешений, *pmode*, применяется к только что созданными файлами только. Новый файл получает указанные настройки разрешений после его первого закрытия. Целочисленное выражение *pmode* содержит одну или обе константы манифеста **_S_IWRITE** и **_S_IREAD**, определенная в SYS\Stat.h. Если заданы обе константы, они объединяются побитовым или оператор ( **&#124;** ). *Pmode* параметра присваивается одно из следующих значений.

|Значение|Определение|
|-----------|----------------|
|**_S_IWRITE**|Разрешена запись.|
|**_S_IREAD**|Разрешено чтение.|
|**_S_IREAD** &AMP;#124; **_S_IWRITE**|Разрешены чтение и запись.|

Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Все файлы всегда доступны для чтения; невозможно предоставить разрешение только на запись. Режимы **_S_IWRITE** и **_S_IREAD** | **_S_IWRITE** затем эквивалентны. Файлы, открытые с помощью **_creat** всегда открывается в режиме совместимости (в разделе [_sopen](sopen-wsopen.md)) с **_SH_DENYNO**.

**_creat** применяет текущую маску разрешений файла к *pmode* перед установкой разрешений (в разделе [_umask](umask.md)). **_creat** предназначена для обеспечения совместимости с предыдущими библиотеками. Вызов **_open** с **_O_CREAT** и **_O_TRUNC** в *oflag* параметр эквивалентен **_creat**и предпочтителен для нового кода.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wcreat**|\<io.h> или \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>См. также

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>

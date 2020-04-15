---
title: Функция _creat, _wcreat
ms.date: 4/2/2020
api_name:
- _creat
- _wcreat
- _o__creat
- _o__wcreat
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
ms.openlocfilehash: 18ecf78d2cbff3647eae912a1bb1b17d5340f185
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348341"
---
# <a name="_creat-_wcreat"></a>Функция _creat, _wcreat

Создает новый файл. **_creat** и **_wcreat** были обезвлечены; использовать [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) вместо.

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

*Имени файла*<br/>
Имя нового файла.

*pmode*<br/>
Настройка разрешений.

## <a name="return-value"></a>Возвращаемое значение

Эти функции при успешном завершении возвращают дескриптор созданного файла. В противном случае функции возвращаются -1 и устанавливают **errno,** как показано в следующей таблице.

|**errno** настройки|Описание|
|---------------------|-----------------|
|**EACCES**|*имя файла* определяет существующий файл только для чтения или указывает каталог вместо файла.|
|**EMFILE**|Больше нет доступных дескрипторов файлов.|
|**ENOENT**|Не удалось найти указанный файл.|

Если *имя файла* **NULL,** эти функции вызывают недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции устанавливают **errno** к **EINVAL** и возвращают -1.

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **_creat** создает новый файл или открывает и уседает существующий. **_wcreat** является широкохарактерным вариантом **_creat;** аргумент *имени файла* для **_wcreat** является широкохарактерной строкой. **_wcreat** и **_creat** ведут себя одинаково иначе.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

Если файл, указанный *именем файла,* не существует, новый файл создается с заданной настройкой разрешения и открывается для записи. Если файл уже существует и его настройка разрешения позволяет писать, **_creat** усечения файла до длины 0, уничтожая предыдущее содержимое, и открывает его для записи. Настройка разрешения, *pmode*, применяется только к вновь созданным файлам. Новый файл получает указанные настройки разрешений после его первого закрытия. В истеже *выражении pmode* содержится одна или обе явные константы **_S_IWRITE** и **_S_IREAD,** определенные в SYS-Stat.h. Когда обе константы даны, они соединены с bitwise или оператором **(&#124;).** Параметр *pmode* устанавливается на одно из следующих значений.

|Значение|Определение|
|-----------|----------------|
|**_S_IWRITE**|Разрешена запись.|
|**_S_IREAD**|Разрешено чтение.|
|**_S_IREAD** **&#124; _S_IWRITE**|Разрешены чтение и запись.|

Если разрешение на запись не предоставлено, файл остается доступным только для чтения. Все файлы всегда доступны для чтения; невозможно предоставить разрешение только на запись. Режимы **_S_IWRITE** и **_S_IREAD** | **_S_IWRITE** затем эквивалентны. Файлы, открытые с использованием **_creat** всегда открываются в режиме совместимости (см. [_sopen)](sopen-wsopen.md)с **_SH_DENYNO.**

**_creat** применяет текущую маску разрешения файла к *pmode* перед установкой разрешений (см. [_umask).](umask.md) **_creat** предоставляется в первую очередь для совместимости с предыдущими библиотеками. Призыв к **_open** с **_O_CREAT** и **_O_TRUNC** в параметре *oflag* эквивалентен **_creat** и предпочтительнее для нового кода.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|
|**_wcreat**|\<io.h> или \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>

---
title: _dupenv_s_dbg, _wdupenv_s_dbg
ms.date: 11/04/2016
api_name:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
ms.openlocfilehash: 6c61986184f93c6cf6e83b33f77dce2bd017cfae
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937681"
---
# <a name="_dupenv_s_dbg-_wdupenv_s_dbg"></a>_dupenv_s_dbg, _wdupenv_s_dbg

Получают значение из текущей среды.  Версии функций [_dupenv_s _wdupenv_s](dupenv-s-wdupenv-s.md), которые выделяют память для предоставления дополнительных сведений об отладке с помощью функции [_malloc_dbg](malloc-dbg.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _dupenv_s_dbg(
   char **buffer,
   size_t *numberOfElements,
   const char *varname,
   int blockType,
   const char *filename,
   int linenumber
);
errno_t _wdupenv_s_dbg(
   wchar_t **buffer,
   size_t * numberOfElements,
   const wchar_t *varname,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Буфер для хранения значения переменной.

*numberOfElements*<br/>
Размер *буфера*.

*varname*<br/>
Имя переменной среды.

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла или **значение NULL**.

*linenumber*<br/>
Номер строки в файле исходного кода или **значение NULL**.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном выполнении, код ошибки при сбое.

Эти функции проверяют свои параметры. Если *buffer* или *имя_переменной* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **функции устанавливают значение** **еинвал** и возвращают **еинвал**.

Если эти функции не могут выделить достаточно памяти, они устанавливают для *buffer* **значение NULL** , а *numberOfElements* — на 0 и возвращают **еномем**.

## <a name="remarks"></a>Примечания

Функции **_dupenv_s_dbg** и **_wdupenv_s_dbg** идентичны **_dupenv_s** и **_wdupenv_s** , за исключением того, что при определении **_DEBUG** эти функции используют отладочную версию [malloc](malloc.md), [_malloc_dbg](malloc-dbg.md), для выделения памяти для значения переменной среды. Сведения о функциях отладки **_malloc_dbg**см. в разделе [_malloc_dbg](malloc-dbg.md).

Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг **_CRTDBG_MAP_ALLOC**. Если определен **_CRTDBG_MAP_ALLOC** , вызовы методов **_dupenv_s** и **_wdupenv_s** пересопоставляются с **_dupenv_s_dbg** и **_wdupenv_s_dbg**соответственно, а *блокктипе* устанавливается в **_NORMAL_BLOCK**. Таким образом, не нужно явно вызывать эти функции, если не нужно помечать блоки кучи как **_CLIENT_BLOCK**. Дополнительные сведения о типах блоков см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s_dbg**|**_dupenv_s_dbg**|**_dupenv_s_dbg**|**_wdupenv_s_dbg**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_dupenv_s_dbg**|\<crtdbg.h>|
|**_wdupenv_s_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_dupenv_s_dbg.c
#include  <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>

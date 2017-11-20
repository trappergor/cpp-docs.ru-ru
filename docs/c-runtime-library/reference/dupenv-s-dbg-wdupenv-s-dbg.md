---
title: "_dupenv_s_dbg, _wdupenv_s_dbg | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
apitype: DLLExport
f1_keywords:
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
dev_langs: C++
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72412790fc7bd71d25d0a77fdb0ede8d7b9e31a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dupenvsdbg-wdupenvsdbg"></a>_dupenv_s_dbg, _wdupenv_s_dbg
Получают значение из текущей среды.  Версии функций [_dupenv_s _wdupenv_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md), которые выделяют память для предоставления дополнительных сведений об отладке с помощью функции [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Буфер для хранения значения переменной.  
  
 `numberOfElements`  
 Размер `buffer`.  
  
 `varname`  
 Имя переменной среды.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя исходного файла или `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле или `NULL`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном выполнении, код ошибки при сбое.  
  
 Эти функции проверяют свои параметры. Если `buffer` или `varname` имеют значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции задают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
 Если этим функциям не удается выделить достаточно памяти, они задают для параметра `buffer` значение `NULL`, а для `numberOfElements` значение 0 и возвращают `ENOMEM`.  
  
## <a name="remarks"></a>Примечания  
 Функции `_dupenv_s_dbg` и `_wdupenv_s_dbg` идентичны `_dupenv_s` и `_wdupenv_s` за исключением того, что если определен флаг `_DEBUG`, эти функции используют отладочную версию функций [malloc](../../c-runtime-library/reference/malloc.md), [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md) для выделения памяти для повторяющейся строки. Сведения о компонентах отладки `_malloc_dbg` см. в разделе [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`. Если определен флаг `_CRTDBG_MAP_ALLOC`, вызовы функций `_dupenv_s` и `_wdupenv_s` повторно сопоставляются с `_dupenv_s_dbg` и `_wdupenv_s_dbg` соответственно, а для параметра `blockType` задается флаг `_NORMAL_BLOCK`. Таким образом, не требуется явно вызывать эти функции, если только нет необходимости пометить блоки кучи как `_CLIENT_BLOCK`. Дополнительные сведения о типах блоков см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tdupenv_s_dbg`|`_dupenv_s_dbg`|`_dupenv_s_dbg`|`_wdupenv_s_dbg`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_dupenv_s_dbg`|\<crtdbg.h>|  
|`_wdupenv_s_dbg`|\<crtdbg.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
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
  
## <a name="sample-output"></a>Пример результатов выполнения  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Константы среды](../../c-runtime-library/environmental-constants.md)   
 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)
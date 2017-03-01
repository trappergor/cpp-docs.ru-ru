---
title: "feof | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- feof
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
- feof
dev_langs:
- C++
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: aef536d11e6d7902bdaf43ccc3a5257be4522661
ms.lasthandoff: 02/24/2017

---
# <a name="feof"></a>feof
Определяет окончание файла в потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `feof` возвращает ненулевое значение, если операция чтения пытается продолжить чтение файла после того, как он закончился; в противном случае возвращается значение 0. Если указателем потока является `NULL`, функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` принимает значение `EINVAL`, а функция `feof` возвращает значение 0.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Подпрограмма `feof` (реализованная и как функция, и как макрос) определяет, пройден ли конец `stream`. Если конец файла пройден, операции чтения возвращают индикатор окончания файла, пока поток не будет закрыт или пока для него не будет вызвана функция `rewind`, `fsetpos`, `fseek` или `clearerr`.  
  
 Например, если файл содержит 10 байт и из него прочитано 10 байт, `feof` возвращает 0, так как, несмотря на то, что указатель файла находится в конце файла, попытка продолжить чтение файла после его окончания еще не предпринималась. Функция `feof` вернет ненулевое значение только после того, как вы попытаетесь прочитать 11-й байт.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`feof`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfeoftxt"></a>Входные данные: crt_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Вывод  
  
```  
Number of bytes read = 19  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)

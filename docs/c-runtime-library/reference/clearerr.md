---
title: "clearerr | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- clearerr
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
- clearerr
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 4f6f82645eba2fc2e1c78ba4dd88751943a62e76
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="clearerr"></a>clearerr
Сбрасывает индикатор ошибки для потока. Существует более безопасная версия этой функции, см. раздел [clearerr_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void clearerr(  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="remarks"></a>Примечания  
 Функция `clearerr` сбрасывает индикатор ошибки и индикатор конечного файла для `stream`. Индикаторы ошибок автоматически не удаляются. После того как индикатор ошибки для указанного потока будет задан, операции в этом потоке будут возвращать значение ошибки до тех пор, пока не будет вызван `clearerr`, `fseek`, `fsetpos` или `rewind`.  
  
 Если параметр `stream` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция задает для `errno` значение `EINVAL` и возвращает его. Дополнительные сведения о `errno` и кодах ошибок см. в разделе [Константы errno](../../c-runtime-library/errno-constants.md).  
  
 Существует более безопасная версия этой функции, см. раздел [clearerr_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`clearerr`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_clearerr.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      clearerr( stdin );  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      clearerr( stdin );  
   }  
   else  
      printf( "No read error\n" );  
}  
```  
  
```Output  
  
n  
  
```  
  
```Output  
  
      nWrite error: No error  
Will input cause an error? n  
No read error  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)

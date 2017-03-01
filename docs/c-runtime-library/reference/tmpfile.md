---
title: "tmpfile | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpfile
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
- tmpfile
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 05edefa97701ebd70d86ff4fc78dc6cee7f083fa
ms.lasthandoff: 02/24/2017

---
# <a name="tmpfile"></a>tmpfile
Создает временный файл. Эта функция устарела, так как появилась более безопасная версия; см. раздел [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
FILE *tmpfile( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения `tmpfile` возвращает указатель на поток. В противном случае возвращается указатель `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `tmpfile` создает временный файл и возвращает указатель на этот поток. Временный файл создается в корневом каталоге. Чтобы создать временный файл в каталоге, отличном от корневого, используйте [tmpnam_s](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) или [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) в сочетании с [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Если не удается открыть файл, `tmpfile` возвращает указатель `NULL`. Этот временный файл удаляется автоматически при закрытии файла, когда программа завершается в обычном режиме или когда вызывается `_rmtmp`, при условии, что текущий рабочий каталог не изменяется. Временный файл открыт в режиме `w+b` (чтение и запись в двоичном файле).  
  
 Сбой может возникать при попытке выполнить более TMP_MAX (см. STDIO.H) вызовов с параметром `tmpfile`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`tmpfile`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
> [!NOTE]
>  В этом примере требуются права администратора для работы в Windows Vista.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)

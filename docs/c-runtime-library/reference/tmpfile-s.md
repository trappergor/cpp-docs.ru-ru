---
title: "tmpfile_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: tmpfile_s
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
f1_keywords: tmpfile_s
dev_langs: C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13d8f3c25a739b212c5977ee44620d8f5966c2f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tmpfiles"></a>tmpfile_s
Создает временный файл. Это версия функции [tmpfile](../../c-runtime-library/reference/tmpfile.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pFilePtr`  
 Адрес указателя для хранения адреса созданного указателя на поток.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0 в случае успеха или код ошибки в случае неудачи.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`pFilePtr`|**Возвращаемое значение**|**Содержимое** `pFilePtr`|  
|----------------|----------------------|---------------------------------|  
|`NULL`|`EINVAL`|не изменено|  
  
 Если возникает ошибка проверки приведенного выше параметра, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, `errno` устанавливается в значение `EINVAL`, и возвращается значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `tmpfile_s` создает временный файл и помещает указатель на этот поток в аргумент `pFilePtr`. Временный файл создается в корневом каталоге. Чтобы создать временный файл в каталоге, отличном от корневого, используйте [tmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) или [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) в сочетании с [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Если не удается открыть файл, `tmpfile_s` записывает `NULL` в параметр `pFilePtr`. Этот временный файл удаляется автоматически при закрытии файла, когда программа завершается в обычном режиме или когда вызывается `_rmtmp`, при условии, что текущий рабочий каталог не изменяется. Временный файл открыт в режиме `w+b` (чтение и запись в двоичном файле).  
  
 Сбой может возникать при попытке выполнить более `TMP_MAX_S` (STDIO.H) вызовов `tmpfile_s.`  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`tmpfile_s`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
> [!NOTE]
>  В этом примере требуются права администратора для работы в Windows Vista.  
  
```  
// crt_tmpfile_s.c  
// This program uses tmpfile_s to create a  
// temporary file, then deletes this file with _rmtmp.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char tempstring[] = "String to be written";  
   int  i;  
   errno_t err;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      err = tmpfile_s(&stream);  
      if( err )  
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
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)
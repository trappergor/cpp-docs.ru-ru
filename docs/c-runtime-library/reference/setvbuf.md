---
title: "setvbuf | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- setvbuf
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
- setvbuf
dev_langs:
- C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: 16
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
ms.openlocfilehash: 3955a2e5c2f0371c804f1b5a7374540ca8720339
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="setvbuf"></a>setvbuf
Управляет потоковой буферизацией и размером буфера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
 `buffer`  
 Выделенный пользователем буфер.  
  
 `mode`  
 Режим буферизации.  
  
 `size`  
 Размер буфера в байтах. Допустимый диапазон: 2 <= `size` <= INT_MAX (2147483647). На внутреннем уровне значение, указанное для `size`, округляется вниз до ближайшего числа, кратного 2.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0 в случае успеха.  
  
 Если `stream` имеет значение `NULL` или `mode`, или `size` не входит в допустимый диапазон, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эта функция возвращает –1 и задает для `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `setvbuf` позволяет программе управлять и буферизацией, и размером буфера для `stream`. Функция `stream` должна ссылаться на открытый файл, для которого не выполнялись операции ввода-вывода с момента его открытия. Массив, на который указывает функция `buffer`, используется в качестве буфера, если он не является `NULL`, в этом случае `setvbuf` использует автоматически выделенный буфер длиной `size`/2 * 2 байтов.  
  
 Должен быть установлен режим `_IOFBF`, `_IOLBF`, или `_IONBF`. Если `mode` имеет значение `_IOFBF` или `_IOLBF`, то `size` используется в качестве размера буфера. Если `mode` имеет значение `_IONBF`, для потока не используется буферизация, и `size` и `buffer` игнорируются. Переменные для функции `mode` и их значения:  
  
 `_IOFBF`  
 Полная буферизация; то есть `buffer` используется в качестве буфера и `size` используется в качестве размера буфера. Если `buffer`имеет значение `NULL`, используется автоматически выделенный буфер длиной в `size` байтов.  
  
 `_IOLBF`  
 В некоторых системах таким образом осуществляется линейная буферизация. Однако для Win32 такое поведение аналогично `_IOFBF`, то есть полной буферизации.  
  
 `_IONBF`  
 Буфер не используется, независимо от функций `buffer` или `size`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`setvbuf`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
'stream1' now has a buffer of 1024 bytes  
'stream2' now has no buffer  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)

---
title: "fflush | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fflush
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
- fflush
dev_langs:
- C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
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
ms.openlocfilehash: f2a11a29ba0eec3c66cf23f72e8fe0e7106d5a5c
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="fflush"></a>fflush
Записывает содержимое потока на диск.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `fflush` возвращает 0, если содержимое буфера было успешно записано на диск. Кроме того, значение 0 также возвращается в случаях, когда указанный поток не имеет буфера или открыт только для чтения. Возвращаемое значение `EOF` указывает на ошибку.  
  
> [!NOTE]
>  Если функция `fflush` возвращает `EOF`, возможна потеря данных из-за ошибки записи. При настройке обработчика критической ошибки лучше всего отключить буферизацию с помощью функции `setvbuf` или использовать процедуры низкоуровневого ввода-вывода, такие как `_open`, `_close` и `_write`, вместо функций ввода-вывода потока.  
  
## <a name="remarks"></a>Примечания  
 Функция `fflush` записывает на диск поток `stream`. Если поток был открыт в режиме записи, а также если он был открыт в режиме обновления и последней была выполнена операция записи, содержимое буфера потока записывается в базовый файл или на базовое устройство, после чего буфер очищается. Если поток был открыт в режиме чтения или не имеет буфера, вызов функции `fflush` не дает никаких результатов, и содержимое буфера сохраняется. Вызов функции `fflush` отменяет результат любого предыдущего вызова функции `ungetc` для потока. После вызова поток остается открытым.  
  
 Если `stream` имеет значение `NULL`, поведение будет таким же, как при вызове функции `fflush` для каждого открытого потока. Выполняется запись на диск всех потоков, открытых в режиме записи, а также всех потоков в режиме обновления, для которых последней была выполнена операция записи. Вызов не влияет на другие потоки.  
  
 Эти буферы обычно обслуживаются операционной системой, которая автоматически определяет оптимальное время записи данных на диск: при заполнении буфера, при закрытии потока или при нормальном завершении программы без закрытия потоков. Предусмотренная в библиотеке времени выполнения возможность фиксации на диск позволяет обеспечить запись критически важных данных непосредственно на диск, а не в буферы операционной системы. Эту возможность можно включить, не переписывая программу, а скомпоновав объектные файлы программы с файлом COMMODE.OBJ. В создаваемом исполняемом файле вызовы функции `_flushall` записывают содержимое всех буферов на диск. Файл COMMODE.OBJ влияет только на функции `_flushall` и `fflush`.  
  
 Дополнительные сведения об управлении возможностью фиксации на диск см. в разделах [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) и [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
 Функция блокирует вызывающий поток, поэтому она потокобезопасна. Сведения о неблокирующей версии см. в описании функции `_fflush_nolock`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fflush`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_fflush.c  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int integer;  
   char string[81];  
  
   // Read each word as a string.  
   printf( "Enter a sentence of four words with scanf: " );  
   for( integer = 0; integer < 4; integer++ )  
   {  
      scanf_s( "%s", string, sizeof(string) );        
      printf( "%s\n", string );  
   }  
  
   // You must flush the input buffer before using gets.   
   // fflush on input stream is an extension to the C standard   
   fflush( stdin );     
   printf( "Enter the same sentence with gets: " );  
   gets_s( string, sizeof(string) );  
   printf( "%s\n", string );  
}  
```  
  
```Output  
  
      This is a test  
This is a test  
  
```  
  
```Output  
  
      This is a test  
This is a testEnter a sentence of four words with scanf: This is a test  
This  
is  
a  
test  
Enter the same sentence with gets: This is a test  
This is a test  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)

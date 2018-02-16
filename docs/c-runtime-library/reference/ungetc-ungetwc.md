---
title: "ungetc, ungetwc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
dev_langs:
- C++
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d65453f1254e4c42658ef6f27d7c90d2ad0022b9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc
Помещает символ обратно в поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Символ, который требуется поместить обратно.  
  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном завершении, каждая из этих функций возвращает символьный аргумент `c`. Если `c` не удается отправить обратно или ни один символ не считан, входной поток не изменяется, и `ungetc` возвращает `EOF`; `ungetwc` возвращает `WEOF`. Если параметр `stream` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если разрешается продолжить выполнение, то возвращается `EOF` или `WEOF`, и для `errno` устанавливается значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `ungetc` помещает символ `c` обратно в `stream` и удаляет индикатор конца файла. Поток должен быть открыт для чтения. Последующие операции чтения на `stream` начинается с `c`. Попытка отправить `EOF` в поток с помощью `ungetc` игнорируется.  
  
 Символы, помещенные в поток с помощью `ungetc`, могут быть удалены, если `fflush`, `fseek`, `fsetpos` или `rewind` вызывается перед считыванием символа из потока. Индикатор позиции в файле будет иметь значение, которое было до помещения символов обратно. Внешнее хранилище, соответствующее потоку, не изменяется. При успешном вызове `ungetc` для текстового потока индикатор позиции в файле будет не задан до тех пор, пока все помещенные обратно символы не будут считаны или удалены. При каждом успешном вызове `ungetc` для двоичного потока индикатор позиции файла уменьшается; если перед вызовом он имел значение 0, то после вызова его значение будет неопределенным.  
  
 Если `ungetc` вызывается дважды без выполнения между вызовами операции чтения или размещения в файле, результаты будут непредсказуемыми. После вызова `fscanf` вызов `ungetc` может завершиться ошибкой, если не будет выполнена другая операция чтения (такая как `getc`). Это обусловлено тем, что `fscanf` сам вызывает `ungetc`.  
  
 `ungetwc` — это версия функции `ungetc` для расширенных символов. Однако при каждом успешном вызове `ungetwc` для текстового или двоичного потока значение индикатора позиции в файле будет не задано до тех пор, пока все помещенные обратно символы не будут считаны или удалены.  
  
 Эти функции являются потокобезопасными и блокируют конфиденциальные данные во время выполнения. Описание неблокирующей версии см. в разделе [_ungetc_nolock, _ungetwc_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`ungetc`|\<stdio.h>|  
|`ungetwc`|\<stdio.h> или \<wchar.h>|  
  
Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout`, и `stderr`, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).
  
## <a name="example"></a>Пример  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
```Output  
  
      521aNumber = 521  
Next character in stream = 'a'  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)
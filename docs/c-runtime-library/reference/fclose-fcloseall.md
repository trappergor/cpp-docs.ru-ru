---
title: "fclose, _fcloseall | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
dev_langs:
- C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 46b9086e4c75a699acec47e3b6b68ba7bcc231cf
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall
Закрывает поток (`fclose`) или все открытые потоки (`_fcloseall`).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `fclose` возвращает 0, если поток был успешно закрыт. Функция `_fcloseall` возвращает общее количество закрытых потоков. Обе функции возвращают `EOF` для указания на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Функция `fclose` закрывает `stream`. Если параметр `stream` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция `fclose` присваивает `errno` значение `EINVAL` и возвращает `EOF`. Всегда проверяйте указатель `stream` перед вызовом этой функции.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Функция `_fcloseall` закрывает все открытые потоки, кроме `stdin`, `stdout`, `stderr` (а в MS-DOS также `_stdaux` и `_stdprn`). Она также закрывает и удаляет все временные файлы, созданные `tmpfile`. При использовании обеих функций все буферы, связанные с потоком, перед закрытием сбрасываются. При закрытии потока выделенные системой буферы освобождаются. Буферы, назначенные пользователем с помощью функций `setbuf` и `setvbuf`, автоматически не освобождаются.  
  
 **Примечание.** При использовании этих функций для закрытия потока вместе с ним закрываются также базовый дескриптор файла и обработчик (или сокет) файла операционной системы. Таким образом, если файл изначально был открыт как обработчик или дескриптор файла и закрыт с помощью функции `fclose`, не следует вызывать функцию `_close`, чтобы закрыть дескриптор файла, и функцию Win32 `CloseHandle`, чтобы закрыть обработчик файла.  
  
 Функции `fclose` и `_fcloseall` включают код для защиты от помех от других потоков. Сведения о неблокирующей версии `fclose` см. в описании функции `_fclose_nolock`.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fclose`|\<stdio.h>|  
|`_fcloseall`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)

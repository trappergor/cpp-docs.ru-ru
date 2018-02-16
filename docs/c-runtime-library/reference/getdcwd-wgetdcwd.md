---
title: "_getdcwd, _wgetdcwd | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _getdcwd
- _wgetdcwd
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
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs:
- C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b74cc20c6f96381d445740db9d41828f28d5a53a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd
Получает полный путь текущей рабочей папки на указанном диске.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `drive`  
 Неотрицательное целое число, которое определяет диск (0 — диск по умолчанию, 1 — A, 2 — B и т. д.).  
  
 Если указанный диск недоступен или невозможно определить тип диска (например, съемный, жесткий, компакт-диск, электронный диск или сетевой диск), вызывается обработчик недопустимых параметров, как описано в разделе [Parameter Validation](../../c-runtime-library/parameter-validation.md).  
  
 `buffer`  
 Место хранения для пути или **NULL**.  
  
 Если указано значение **NULL** , эта функция выделяет буфер размером не менее `maxlen` с помощью функции **malloc**и возвращаемое значение функции `_getdcwd` представляет собой указатель на выделенный буфер. Буфер может быть освобожден с помощью вызова функции `free` и передачи ему указателя.  
  
 `maxlen`  
 Отличное от нуля положительное целое число, определяющее максимальную длину пути, в символах: `char` для функции `_getdcwd` и `wchar_t` для функции `_wgetdcwd`.  
  
 Если указано значение `maxlen` не больше нуля, то вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, которая представляет полный путь текущей рабочей папки на указанном диске, или значение `NULL`, что указывает на ошибку.  
  
 Если для параметра `buffer` указано значение `NULL` и недостаточно памяти для выделения памяти под `maxlen` символов, возникает ошибка и параметр `errno` принимает значение `ENOMEM`. Если длина пути, включая завершающий нуль-символ, превышает значение `maxlen`, возникает ошибка и параметр `errno` принимает значение `ERANGE`. Дополнительные сведения об этих кодах ошибки см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_getdcwd` получает полный путь текущей рабочей папки на указанном диске и сохраняет его в параметре `buffer`. Если текущей рабочей папкой является корневой каталог, строка заканчивается обратной косой чертой (\\). Если текущая рабочая папка находится в каталоге, отличном от корневого, строка заканчивается именем каталога, а не обратной косой чертой.  
  
 `_wgetdcwd` — это версия функции `_getdcwd`для расширенных символов, ее параметр `buffer` и возвращаемое значение представляют собой строки расширенных символов. В противном случае поведение `_wgetdcwd` и `_getdcwd` идентично.  
  
 Эта функция потокобезопасна, даже если она зависит от функции **GetFullPathName**, которая сама не потокобезопасна. Однако можно нарушить потокобезопасность, если многопоточное приложение вызывает и эту функцию, и функцию **GetFullPathName**. Дополнительные сведения см. на сайте [Библиотека MSDN](http://go.microsoft.com/fwlink/p/?linkid=150542) , выполнив поиск с запросом **GetFullPathName**.  
  
 Версия этой функции с суффиксом `_nolock` работает идентично этой функции, за исключением того, что она не потокобезопасна и не защищена от помех со стороны других потоков. Для получения дополнительной информации см. [_getdcwd_nolock, _wgetdcwd_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md).  
  
 Если заданы параметры `_DEBUG` и `_CRTDBG_MAP_ALLOC` , вызовы функций `_getdcwd` и `_wgetdcwd` заменяются вызовами функций `_getdcwd_dbg` и `_wgetdcwd_dbg` , что обеспечивает возможность отладки выделения памяти. Дополнительные сведения см. в разделе[_getdcwd_dbg, _wgetdcwd_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_getdcwd`|\<direct.h>|  
|`_wgetdcwd`|\<direct.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. пример в разделе [_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## <a name="see-also"></a>См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)
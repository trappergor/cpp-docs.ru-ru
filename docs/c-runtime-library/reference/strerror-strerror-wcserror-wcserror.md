---
title: "strerror, _strerror, _wcserror, __wcserror | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
dev_langs: C++
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b534c0a43c78c42265fa3b36aca523dc27e170fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror
Получает системную строку сообщения об ошибке (`strerror`, `_wcserror`) или форматирует пользовательскую строку сообщения об ошибке (`_strerror`, `__wcserror`). Существуют более безопасные версии этих функций; см. раздел [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *strerror(  
   int errnum   
);  
char *_strerror(  
   const char *strErrMsg   
);  
wchar_t * _wcserror(  
   int errnum   
);  
wchar_t * __wcserror(  
   const wchar_t *strErrMsg   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `errnum`  
 Номер ошибки.  
  
 `strErrMsg`  
 Пользовательское сообщение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Все эти функции возвращают указатель на строку сообщения об ошибке. Последующие вызовы могут перезаписать строку.  
  
## <a name="remarks"></a>Примечания  
 Функция `strerror` сопоставляет `errnum` со строкой сообщения об ошибке и возвращает указатель на строку. Фактически ни `strerror`, ни `_strerror` не печатают сообщение. Для этого необходимо вызвать функцию вывода, такую как [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md):  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 Если `strErrMsg` передается как `NULL`, `_strerror` возвращает указатель на строку, которая содержит системное сообщение об ошибке для последнего вызова библиотеки, который создал ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если значение `strErrMsg` не равно `NULL`, `_strerror` возвращает указатель на строку, содержащую (по порядку) сообщение строки, двоеточие, пробел, системное сообщение об ошибке для последнего вызова библиотеки, создавшего ошибку, и символ новой строки. Длина сообщения строки не должна превышать 94 символа.  
  
 Фактический номер ошибки для `_strerror` хранится в переменной [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Чтобы обеспечить точные результаты, вызывайте `_strerror` сразу после того, как подпрограмма библиотеки возвращает ошибку. В противном случае последующие вызовы `strerror` или `_strerror` могут перезаписать значение `errno`.  
  
 `_wcserror` и `__wcserror` — это версии `strerror` и `_strerror` с расширенными символами.  
  
 `_strerror`, `_wcserror` и `__wcserror` не входят в определение ANSI. Они являются расширениями Майкрософт, и мы не рекомендуем использовать их в ситуациях, когда требуется создать переносимый код. Для совместимости с ANSI вместо них рекомендуется использовать `strerror`.  
  
 Для получения строк ошибок рекомендуется использовать `strerror` или `_wcserror` вместо нерекомендуемых макросов [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) и внутренних функций `__sys_errlist` и `__sys_nerr`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strerror`|\<string.h>|  
|`_strerror`|\<string.h>|  
|`_wcserror`, `__wcserror`|\<string.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 См. пример для [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)
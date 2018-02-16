---
title: "strerror_s, _strerror_s, _wcserror_s, __wcserror_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- __wcserror_s
- _strerror_s
- _wcserror_s
- strerror_s
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
- wcserror_s
- __wcserror_s
- _tcserror_s
- _wcserror_s
- tcserror_s
- strerror_s
- _strerror_s
dev_langs:
- C++
helpviewer_keywords:
- __wcserror_s function
- error messages, printing
- tcserror_s function
- printing error messages
- strerror_s function
- _wcserror_s function
- _tcserror_s function
- _strerror_s function
- wcserror_s function
- error messages, getting
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 791f9b7408fded070fe61206d4303c26c8926d3e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="strerrors-strerrors-wcserrors-wcserrors"></a>strerror_s, _strerror_s, _wcserror_s, __wcserror_s
Получают системное сообщение об ошибке (`strerror_s`, `_wcserror_s`) или выводят указанное пользователем сообщение об ошибке (`_strerror_s`, `__wcserror_s`). Это версии функций [strerror, _strerror, _wcserror, \__wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Буфер для строки ошибки.  
  
 `numberOfElements`  
 Размер буфера.  
  
 `errnum`  
 Номер ошибки.  
  
 `strErrMsg`  
 Пользовательское сообщение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль в случае успеха или код ошибки в случае неудачи.  
  
### <a name="error-condtions"></a>Условия ошибки  
  
|`buffer`|`numberOfElements`|`strErrMsg`|Содержимое `buffer`|  
|--------------|------------------------|-----------------|--------------------------|  
|`NULL`|any|any|Н/Д|  
|any|0|any|не изменено|  
  
## <a name="remarks"></a>Примечания  
 Функция `strerror_s` сопоставляет параметр `errnum` со строкой сообщения об ошибке, возвращая строку в `buffer`. `_strerror_s` не принимает номер ошибки; она использует текущее значение `errno` для определения соответствующего сообщения. Ни функция `strerror_s`, ни функция `_strerror_s` не выполняют фактическую печать сообщения. Для этого необходимо вызвать функцию вывода, например [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md):  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 Если `strErrMsg` имеет значение `NULL`, функция `_strerror_s` возвращает строку в `buffer`, содержащую системное сообщение об ошибке для последнего вызова библиотеки, вызвавшего ошибку. Строка сообщения об ошибке оканчивается символом новой строки ('\n'). Если параметр `strErrMsg` не имеет значение `NULL`, функция `_strerror_s` возвращает строку в `buffer`, содержащую (в указанном порядке) строку сообщения, двоеточие, пробел, системное сообщение об ошибке для последнего вызова библиотеки, вызвавшего ошибку, и символ новой строки. Длина сообщения строки не должна превышать 94 символа.  
  
 Эти функции усекают сообщение об ошибке, если его длина превышает `numberOfElements` –1. Результирующая строка в `buffer` всегда завершается символом NULL.  
  
 Фактический номер ошибки для `_strerror_s` хранится в переменной [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Доступ к системным сообщениям об ошибках осуществляется через переменную [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), которая представляет собой массив сообщений об ошибке, отсортированный по номеру ошибки. Функция `_strerror_s` получает доступ к соответствующему сообщению об ошибке, используя значение `errno` в качестве индекса для массива `_sys_errlist`. Значение переменной [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) определено как максимальное количество элементов в массиве `_sys_errlist`. Чтобы обеспечить точные результаты, вызывайте `_strerror_s` сразу после того, как подпрограмма библиотеки возвращает ошибку. В противном случае последующие вызовы `strerror_s` или `_strerror_s` могут перезаписать значение `errno`.  
  
 `_wcserror_s` и `__wcserror_s` — это версии `strerror_s` и `_strerror_s` с расширенными символами.  
  
 Эти функции проверяют свои параметры. Если буфер имеет значение `NULL`, параметр размера равен 0, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают `EINVAL` и устанавливают параметр `errno` в значение `EINVAL`.  
  
 `_strerror_s`, `_wcserror_s`, и `__wcserror_s` не входят в определение ANSI, а представляют собой расширения Microsoft к нему. Их не следует использовать там, где требуется переносимость; для обеспечения совместимости с ANSI используйте функцию `strerror_s`.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`strerror_s`, `_strerror_s`|\<string.h>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)
---
title: "tmpnam_s _wtmpnam_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpnam_s
- _wtmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs:
- C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 20
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
ms.openlocfilehash: c2a7276c8670bf0a3fd56ac8c0df111e82da16de
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s
Формирует имена, которые можно использовать для создания временных файлов. Это версии функций [tmpnam и _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `str`  
 Указатель, который будет содержать сформированное имя.  
  
 [in] `sizeInChars`  
 Размер буфера в символах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Обе эти функции возвращают 0 в случае успеха или номер ошибки в случае сбоя.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**Возвращаемое значение**|**Содержимое** `str`|  
|`NULL`|любые|`EINVAL`|не изменено|  
|не `NULL` (указывает на допустимую память)|слишком короткий|`ERANGE`|не изменено|  
  
 Если параметр `str` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Каждая из этих функций возвращает имя файла, который в данный момент не существует. Функция `tmpnam_s` возвращает имя, уникальное в рамках текущего рабочего каталога. Заметьте, что если в начало имени файла добавляется обратная косая черта без сведений о пути, например \fname21, это означает, что имя является допустимым для текущей рабочей папки.  
  
 В случае функции `tmpnam_s` это сформированное имя файла можно сохранить в параметре `str`. Максимальная длина строки, возвращенной `tmpnam_s` — `L_tmpnam_s` (задано в STDIO.H). Если параметр `str` имеет значение `NULL`, функция `tmpnam_s` оставляет результат во внутреннем статическом буфере. Поэтому все последующие вызовы уничтожают это значение. Имя, созданное функцией `tmpnam_s`, состоит из программно формируемого имени файла и, после первого вызова функции `tmpnam_s`, расширения файла из последовательных чисел с основанием 32 (.1-.1vvvvvu, где `TMP_MAX_S` в STDIO.H задан как INT_MAX).  
  
 Функция `tmpnam_s` автоматически обрабатывает многобайтовые строковые аргументы должным образом, распознавая последовательности многобайтовых символов согласно кодовой странице OEM, полученной из операционной системы. `_wtmpnam_s` — это версия с расширенными символами для `tmpnam_s`; аргумент и возвращаемое значение `_wtmpnam_s` являются строками с расширенными символами. В остальных отношениях поведение функций `_wtmpnam_s` и `tmpnam_s` идентично, за исключением того, что функция `_wtmpnam_s` не обрабатывает многобайтовые строки.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`tmpnam_s`|\<stdio.h>|  
|`_wtmpnam_s`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)

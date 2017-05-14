---
title: "_searchenv_s, _wsearchenv_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsearchenv_s
- _searchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs:
- C++
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
caps.latest.revision: 32
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 3b7b1d4165edb3a7e34cda665de195759784eedc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s
Ищет файл, используя пути в среде. Это версии функций [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md) с повышенной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char *pathname,  
   size_t numberOfElements  
);  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t *pathname,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _searchenv_s(  
   const char *filename,  
   const char *varname,  
   char (&pathname)[size]  
); // C++ only  
template <size_t size>  
errno_t _wsearchenv_s(  
   const wchar_t *filename,  
   const wchar_t *varname,  
   wchar_t (&pathname)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `filename`  
 Имя искомого файла.  
  
 [in] `varname`  
 Искомая среда.  
  
 [выходной] `pathname`  
 Буфер для хранения полного пути.  
  
 [in] `numberOfElements`  
 Размер `pathname` буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае неудачи.  
  
 Если `filename` является пустой строкой, возвращаемое значение — `ENOENT`.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`filename`|`varname`|`pathname`|`numberOfElements`|Возвращаемое значение|Содержимое `pathname`|  
|----------------|---------------|----------------|------------------------|------------------|----------------------------|  
|any|любые|`NULL`|any|`EINVAL`|Н/Д|  
|`NULL`|любые|любые|любые|`EINVAL`|не изменено|  
|any|любые|any|<= 0|`EINVAL`|не изменено|  
  
 Если выполняется какое-либо из этих условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Процедура `_searchenv_s` ищет целевой файл в указанном домене. Переменной `varname` может быть любая переменная среды или переменная, определяемая пользователем и определяющая список путей к каталогам, например `PATH`, `LIB` и `INCLUDE`. Поскольку процедура `_searchenv_s` чувствительна к регистру, значение параметра `varname` должно соответствовать регистру переменной среды. Если `varname` не соответствует имени переменной среды, определенному в среде процесса, функция возвращает нуль и переменная `pathname` остается неизменной.  
  
 Сначала процедура выполняет поиск файла в текущем рабочем каталоге. Если файл не найден, его поиск продолжается в каталогах, указанных в переменной среды. Если целевой файл содержится в одном из этих каталогов, созданный путь копируется в `pathname`. Если файл `filename` не найден, `pathname` содержит пустую строку с завершающим нулем.  
  
 Буфер `pathname` должен содержать не меньше `_MAX_PATH` знаков, чтобы вместить полное имя созданного пути. В противном случае `_searchenv_s` может вызвать переполнение буфера `pathname` и привести к непредвиденному поведению.  
  
 `_wsearchenv_s` — это двухбайтовая версия `_searchenv_s`; аргументы для `_wsearchenv_s` представляют собой двухбайтовые строки. Поведение `_wsearchenv_s` и `_searchenv_s` идентично в противном случае.  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tsearchenv_s`|`_searchenv_s`|`_searchenv_s`|`_wsearchenv_s`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_searchenv_s`|\<stdlib.h>|  
|`_wsearchenv_s`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_searchenv_s.c  
/* This program searches for a file in  
 * a directory specified by an environment variable.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char pathbuffer[_MAX_PATH];  
   char searchfile[] = "CL.EXE";  
   char envvar[] = "PATH";  
   errno_t err;  
  
   /* Search for file in PATH environment variable: */  
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );  
   if (err != 0)  
   {  
      printf("Error searching the path. Error code: %d\n", err);  
   }  
   if( *pathbuffer != '\0' )  
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );  
   else  
      printf( "%s not found\n", searchfile );  
}  
```  
  
```Output  
Path for CL.EXE:  
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE  
```  
  
## <a name="see-also"></a>См. также  
 [Управление каталогами](../../c-runtime-library/directory-control.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md)

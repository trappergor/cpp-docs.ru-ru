---
title: "_splitpath_s, _wsplitpath_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath_s
- _splitpath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3b4b1a35e2abcbeb128a36443eb4c5e5aa2a15e9
ms.lasthandoff: 02/24/2017

---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s
Разбивает имя пути на компоненты. Это версии функции [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `path`  
 Полный путь.  
  
 [выходной] `drive`  
 Буква диска с двоеточием в конце (`:`). Если буква диска не требуется, для этого параметра можно передать значение `NULL`.  
  
 [in] `driveNumberOfElements`  
 Размер буфера `drive` в однобайтовых или расширенных символах. Если параметр `drive` имеет значение `NULL`, это значение должно быть 0.  
  
 [выходной] `dir`  
 Путь к каталогу, включая заключительную косую черту. Могут использоваться символы косой черты (`/`), обратной косой черты (`\`) или оба. Если путь к каталогу не требуется, для этого параметра можно передать значение `NULL`.  
  
 [in] `dirNumberOfElements`  
 Размер буфера `dir` в однобайтовых или расширенных символах. Если параметр `dir` имеет значение `NULL`, это значение должно быть 0.  
  
 [выходной] `fname`  
 Базовое имя файла (без расширения). Если имя файла не требуется, для этого параметра можно передать значение `NULL`.  
  
 [in] `nameNumberOfElements`  
 Размер буфера `fname` в однобайтовых или расширенных символах. Если параметр `fname` имеет значение `NULL`, это значение должно быть 0.  
  
 [выходной] `ext`  
 Расширение имени файла, включая ведущую точку (**.**). Если расширение имени файла не требуется, для данного параметра можно передать значение `NULL`.  
  
 [in] `extNumberOfElements`  
 Размер буфера `ext` в однобайтовых или расширенных символах. Если параметр `ext` имеет значение `NULL`, это значение должно быть 0.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успеха или код ошибки в случае неудачи.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|Условие|Возвращаемое значение|  
|---------------|------------------|  
|`path` равно `NULL`|`EINVAL`|  
|`drive` имеет значение `NULL`, `driveNumberOfElements` отличен от нуля|`EINVAL`|  
|`drive` отличен от `NULL`, `driveNumberOfElements` равен нулю|`EINVAL`|  
|`dir` имеет значение `NULL`, `dirNumberOfElements` отличен от нуля|`EINVAL`|  
|`dir` отличен от `NULL`, `dirNumberOfElements` равен нулю|`EINVAL`|  
|`fname` имеет значение `NULL`, `nameNumberOfElements` отличен от нуля|`EINVAL`|  
|`fname` отличен от `NULL`, `nameNumberOfElements` равен нулю|`EINVAL`|  
|`ext` имеет значение `NULL`, `extNumberOfElements` отличен от нуля|`EINVAL`|  
|`ext` отличен от `NULL`, `extNumberOfElements` равен нулю|`EINVAL`|  
  
 Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
 Если какой-либо из этих буферов слишком мал для хранения результата, эти функции очищают все буферы, присваивают им пустые строки, устанавливают для параметра `errno` значение `ERANGE` и возвращают `ERANGE`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_splitpath_s` разделяет путь на четыре компонента. Функция `_splitpath_s` автоматически требуемым образом обрабатывает аргументы в виде многобайтовых строк, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей. `_wsplitpath_s` — это двухбайтовая версия `_splitpath_s`; аргументы для `_``wsplitpath_s` представляют собой двухбайтовые строки. В остальном эти функции ведут себя одинаково.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 Каждый компонент полного пути сохраняется в отдельном буфере; константы манифеста `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` и `_MAX_EXT` (определены в файле STDLIB.H) определяют максимальный допустимый размер каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.  
  
 В приведенной ниже таблице перечислены значения констант манифеста.  
  
|Имя|Значение|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Если полный путь не содержит некоторый компонент (например, имя файла), функция `_splitpath_s` присваивает соответствующему буферу пустую строку.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_splitpath_s`|\<stdlib.h>|  
|`_wsplitpath_s`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)

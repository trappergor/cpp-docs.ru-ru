---
title: "_splitpath, _wsplitpath | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
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
ms.openlocfilehash: bbd6a163df9daf8e699f3ecf52325786fe89d8ea
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath
Разбивают имя пути на компоненты. Существуют более безопасные версии этих функций; см. раздел [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _splitpath(  
   const char *path,  
   char *drive,  
   char *dir,  
   char *fname,  
   char *ext   
);  
void _wsplitpath(  
   const wchar_t *path,  
   wchar_t *drive,  
   wchar_t *dir,  
   wchar_t *fname,  
   wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `path`  
 Полный путь.  
  
 `drive`  
 Буква диска с двоеточием в конце (`:`). Если буква диска не требуется, для этого параметра можно передать значение `NULL`.  
  
 `dir`  
 Путь к каталогу, включая заключительную косую черту. Могут использоваться символы косой черты (`/`), обратной косой черты (`\`) или оба. Если путь к каталогу не требуется, для этого параметра можно передать значение `NULL`.  
  
 `fname`  
 Базовое имя файла (без расширения). Если имя файла не требуется, для этого параметра можно передать значение `NULL`.  
  
 `ext`  
 Расширение имени файла, включая начальную точку (`.`). Если расширение имени файла не требуется, для этого параметра можно передать значение `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_splitpath` разделяет путь на четыре компонента. Функция `_splitpath` автоматически требуемым образом обрабатывает аргументы в виде многобайтовых строк, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей. `_wsplitpath` — это двухбайтовая версия `_splitpath`; аргументы для `_wsplitpath` представляют собой двухбайтовые строки. В остальном эти функции ведут себя одинаково.  
  
 **Примечание о безопасности.** Эти функции предполагают потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795). Существуют более безопасные версии этих функций; см. раздел [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 Каждый компонент полного пути сохраняется в отдельном буфере; константы манифеста `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` и `_MAX_EXT` (определены в файле STDLIB.H) определяют максимальный размер каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.  
  
 Каждый буфер должен быть соразмерен соответствующей константе манифеста, чтобы избежать потенциального переполнения буфера.  
  
 В приведенной ниже таблице перечислены значения констант манифеста.  
  
|Имя|Значение|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Если полный путь не содержит некоторый компонент (например, имя файла), функция `_splitpath` присваивает соответствующим буферам пустые строки.  
  
 Можно передать `NULL` для `_splitpath` для любого параметра, отличного от `path`, который не требуется.  
  
 Если параметр `path` имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_splitpath`|\<stdlib.h>|  
|`_wsplitpath`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 См. пример для функции [_makepath](../../c-runtime-library/reference/makepath-wmakepath.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)

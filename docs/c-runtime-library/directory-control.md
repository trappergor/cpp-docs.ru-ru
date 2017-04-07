---
title: "Управление каталогами | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
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
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 00a892376691f0d73b6ce0483cccf8bb063c43b4
ms.lasthandoff: 03/30/2017

---
# <a name="directory-control"></a>Управление каталогами
Эти подпрограммы имеют доступ к структуре каталогов, изменяют ее и получают о ней сведения.  
  
### <a name="directory-control-routines"></a>Подпрограммы управления каталогами  
  
|Подпрограмма|Применение|  
|-------------|---------|  
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Изменение текущей рабочей папки|  
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Изменение текущего диска|  
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Получение текущей рабочей папки для диска по умолчанию|  
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Получение текущей рабочей папки для выбранного диска|  
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Заполняет структуру `_diskfree_t` сведениями о диске.|  
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Получение текущего диска (по умолчанию)|  
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Возвращает битовую маску, которая представляет доступные в данный момент диски.|  
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Создание нового каталога|  
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Удалить каталог|  
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Поиск выбранного файла в указанных папках|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [Обработка файлов](../c-runtime-library/file-handling.md)   
 [Системные вызовы](../c-runtime-library/system-calls.md)

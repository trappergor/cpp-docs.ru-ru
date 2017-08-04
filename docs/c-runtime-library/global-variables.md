---
title: "Глобальные переменные | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.variables
dev_langs:
- C++
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
caps.latest.revision: 15
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b4fb921a0685181aa3cd4dd2cf0422e3d6256ac5
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="global-variables"></a>Глобальные переменные
Библиотека времени выполнения языка C (Майкрософт) обеспечивает следующие глобальные переменные или макросы. Многие из этих глобальных переменных или макросов были признаны нерекомендуемыми и заменены более надежными и безопасными функциональными версиями, которые мы рекомендуем использовать вместо них.  
  
|Переменная|Описание|  
|--------------|-----------------|  
|[__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)|Содержит аргументы командной строки.|  
|[_daylight, _dstbias, _timezone, and _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Не рекомендуется. Используйте `_get_daylight`, `_get_dstbias`, `_get_timezone` и `_get_tzname`.<br /><br /> Вносит корректировку для локального времени; используется в некоторых функциях даты и времени.|  
|[errno, _doserrno, _sys_errlist, and _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|Не рекомендуется. Используйте `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` и `strerror`.<br /><br /> Хранит коды ошибок и связанные сведения.|  
|[_environ, _wenviron](../c-runtime-library/environ-wenviron.md)|Не рекомендуется. Используйте `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s` и `_wputenv_s`.<br /><br /> Указывает на массив указателей на строки среды процесса; инициализация при запуске.|  
|[_fmode](../c-runtime-library/fmode.md)|Не рекомендуется. Используйте `_get_fmode` или `_set_fmode`.<br /><br /> Задает режим преобразования файлов по умолчанию.|  
|[_iob](../c-runtime-library/iob.md)|Массив структур управления вводом-выводом для консоли, файлов и устройств.|  
|[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Содержит сведения, используемые функциями классификации символов.|  
|[_pgmptr, _wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Не рекомендуется. Используйте `_get_pgmptr` или `_get_wpgmptr`.<br /><br /> Инициализируется при запуске программы до полного или относительного пути программы, полного имени программы или имени программы без расширения имени файла (в зависимости от способа вызова программы).|  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)   
 [__argc, \__argv, \__wargv](../c-runtime-library/argc-argv-wargv.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [_get_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [_get_errno](../c-runtime-library/reference/get-errno.md)   
 [_set_errno](../c-runtime-library/reference/set-errno.md)   
 [_dupenv_s, _wdupenv_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)

---
title: "_putenv, _wputenv | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _putenv
- _wputenv
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
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
dev_langs:
- C++
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 22
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
ms.openlocfilehash: d91f7b780c8f17fbe1e12a195b6a7cf2eaad3d2f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="putenv-wputenv"></a>_putenv, _wputenv
Создает, изменяет или удаляет переменные среды. Существуют более безопасные версии этих функций; см. статью [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md).  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `envstring`  
 Определение строки среды.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0 в случае успеха или значение -1 в случае ошибки.  
  
## <a name="remarks"></a>Примечания  
 Функция `_putenv` добавляет новые переменные среды или изменяет значения существующих переменных среды. Переменные среды определяют среду, в которой выполняется процесс (например, путь поиска по умолчанию для библиотек, связываемых с программой). `_wputenv` — это версия `_putenv` с расширенными символами; аргумент `envstring` для `_wputenv` — строка расширенных символов.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 Аргумент `envstring` должен быть указателем на строку вида `varname=string`, где `varname` — имя добавляемой или изменяемой переменной среды, а `string` — значение переменной. Если переменная `varname` уже существует в среде, ее значение заменяется значением `string`; в противном случае в эту среду добавляются новая переменная `varname` и ее значение `string`. Можно удалить переменную среды, указав пустой параметр `string` — другими словами, указав только `varname=`.  
  
 Функции `_putenv` и `_wputenv` затрагивают только локальную среду текущего процесса; их нельзя использовать для изменения среды командного уровня. Таким образом, эти функции работают только в структурах данных, доступных библиотеке среды выполнения, а не в сегменте среды, созданном для процесса операционной системой. При завершении текущего процесса среда возвращается на уровень вызывающего процесса (в большинстве случаев — на уровень операционной системы). Однако измененную среду можно передать любым новым процессам, создаваемым функцией `_spawn`, `_exec` или `system`, и эти новые процессы получают все новые элементы, добавленные функциями `_putenv` и `_wputenv`.  
  
 Не изменяйте запись среды напрямую: вместо этого используйте для изменения среды функцию `_putenv` или `_wputenv`. В частности, непосредственное освобождение элементов глобального массива `_environ[]` может привести к адресации недопустимой памяти.  
  
 Функции `getenv` и `_putenv` используют глобальную переменную `_environ` для доступа к таблице среды; функции `_wgetenv` и `_wputenv` используют таблицу `_wenviron`. `_putenv`и `_wputenv` может изменить значение `_environ` и `_wenviron`, таким образом делая недействительным `_envp` аргумент `main` и `_wenvp` аргумент `wmain`. Следовательно, для получения данных о среде безопаснее использовать `_environ` или `_wenviron`. Дополнительные сведения о связи функций `_putenv` и `_wputenv` с глобальными переменными см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Семейства функций `_putenv` и `_getenv` не являются потокобезопасными. Функция `_getenv` может вернуть указатель строки, в то время как функция `_putenv` изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_putenv`|\<stdlib.h>|  
|`_wputenv`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 Пример использования функции `_putenv` см. в разделе [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)

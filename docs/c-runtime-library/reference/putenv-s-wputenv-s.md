---
title: "_putenv_s, _wputenv_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wputenv_s
- _putenv_s
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
apitype: DLLExport
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
dev_langs:
- C++
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
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
ms.openlocfilehash: fc06fd348f1fce9e9eb9fe36bc976460fc57d884
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="putenvs-wputenvs"></a>_putenv_s, _wputenv_s
Создает, изменяет или удаляет переменные среды. Это версии функций [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/en-us/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _putenv_s(  
   const char *name,  
   const char *value   
);  
errno_t _wputenv_s(  
   const wchar_t *name,  
   const wchar_t *value  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `name`  
 Имя переменной среды.  
  
 `value`  
 Значение, которое будет задано для переменной среды.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0 в случае успешного выполнения операции или код ошибки.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`name`|`value`|Возвращаемое значение|  
|------------|-------------|------------------|  
|`NULL`|любые|`EINVAL`|  
|любые|`NULL`|`EINVAL`|  
  
 Если возникает одно из условий ошибки, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции возвращают `EINVAL` и устанавливают для `errno` значение `EINVAL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_putenv_s` добавляет новые переменные среды или изменяет значения существующих переменных среды. Переменные среды определяют среду, в которой выполняется процесс (например, путь поиска по умолчанию для библиотек, связываемых с программой). `_wputenv_s` — это версия `_putenv_s` с расширенными символами; аргумент `envstring` для `_wputenv_s` — строка расширенных символов.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tputenv_s`|`_putenv_s`|`_putenv_s`|`_wputenv_s`|  
  
 `name` — это имя добавляемой или изменяемой переменной среды, а `value` — это значение переменной. Если переменная `name` уже существует в среде, ее значение заменяется значением `value`; в противном случае в среду добавляется новая переменная `name` и ее значение `value`. Можно удалить переменную среды, указав в качестве `value` пустую строку ("").  
  
 Функции `_putenv_s` и `_wputenv_s` затрагивают только локальную среду текущего процесса; их нельзя использовать для изменения среды командного уровня. Эти функции работают только в структурах данных, доступных библиотеке времени выполнения, а не в "сегменте" среды, созданном для процесса операционной системой. По завершении текущего процесса среда возвращается на уровень вызывающего процесса; в большинстве случаев это уровень операционной системы. Однако измененную среду можно передать любым новым процессам, созданным функциями `_spawn`, `_exec` или `system`, и эти новые процессы получат все новые элементы, добавленные функциями `_putenv_s` и `_wputenv_s`.  
  
 Не изменяйте запись среды напрямую; вместо этого используйте для изменения среды функцию `_putenv_s` или `_wputenv_s`. В частности, непосредственное освобождение элементов глобального массива `_environ[]` может привести к адресации недопустимого участка памяти.  
  
 Функции `getenv` и `_putenv_s` используют глобальную переменную `_environ` для доступа к таблице среды; функции `_wgetenv` и `_wputenv_s` используют таблицу `_wenviron`. Функции `_putenv_s` и `_wputenv_s` могут изменить значение `_environ` и `_wenviron` и тем самым сделать недействительным аргумент `envp` для `main` и аргумент `_wenvp` для `wmain`. Следовательно, для получения данных о среде безопаснее использовать `_environ` или `_wenviron`. Дополнительные сведения о связи функций `_putenv_s` и `_wputenv_s` с глобальными переменными см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Семейства функций `_putenv_s` и `_getenv_s` не являются потокобезопасными. Функция `_getenv_s` может возвратить строковый указатель в то время как `_putenv_s` изменяет строку, что может вызвать случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_putenv_s`|\<stdlib.h>|  
|`_wputenv_s`|\<stdlib.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
 Пример, в котором показано, как использовать функцию `_putenv_s`, см. в разделе [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)

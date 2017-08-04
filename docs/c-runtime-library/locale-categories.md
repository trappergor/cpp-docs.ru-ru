---
title: "Категории языковых стандартов | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
dev_langs:
- C++
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: 7
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
ms.openlocfilehash: dcb4fe96d79ed7b66814c33ecda5d2f68481a4fa
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="locale-categories"></a>Категории языковых стандартов
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <locale.h>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Категории языковых стандартов представляют собой константы манифеста, с помощью которых подпрограммы локализации указывают, какую информацию о языковом стандарте программы они будут использовать. Языковой стандарт определяет расположение (или страну, или регион), для которого можно настроить определенные аспекты программы. Например, языковой стандарт влияет на форматирование дат и отображение денежных значений.  
  
|Категории языкового стандарта|Части программы, на которые они влияют|  
|---------------------|-------------------------------|  
|`LC_ALL`|Любое применение языкового стандарта (все категории)|  
|`LC_COLLATE`|Поведение функций `strcoll` и `strxfrm`|  
|`LC_CTYPE`|Поведение функций обработки символов (за исключением **isdigit**, `isxdigit`, `mbstowcs` и `mbtowc`)|  
|`LC_MAX`|Аналогично `LC_TIME`|  
|`LC_MIN`|Аналогично `LC_ALL`|  
|`LC_MONETARY`|Информация о форматировании денежных значений, возвращаемая функцией `localeconv`|  
|`LC_NUMERIC`|Символ десятичного разделителя для процедур форматированного вывода (например, `printf`), для процедур преобразования данных и для форматирования в выводе функции `localeconv`, не имеющего отношения к денежным значениям.|  
|`LC_TIME`|Поведение функции `strftime`|  
  
 См. пример в описании функций [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
## <a name="see-also"></a>См. также  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [Функции strcoll](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)

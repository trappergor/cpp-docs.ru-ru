---
title: "Класс ctype_base | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::ctype_base
- ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 74c13251b63018e00490487cb9a45c4bb6d52a21
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ctypebase-class"></a>Класс ctype_base
Этот класс служит в качестве базового класса для аспектов класса шаблона [ctype](../standard-library/ctype-class.md). Базовый класс для класса ctype, используемый для определения типов перечисления, применяемых для классификации или тестирования символов по отдельности или целыми диапазонами.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ctype_base : public locale::facet
{
    enum
 {
    alnum,
 alpha,
    cntrl,
 digit,
    graph,
 lower,
    print,
 punct,
    space,
 upper,
    xdigit
 };
    typedef short mask;
    ctype_base(
 size_t _Refs = 0);

 ~ctype_base();

};
```  
  
## <a name="remarks"></a>Примечания  
 Задает маску перечисления. Каждая константа перечисления характеризует другой способ классификации символов, в соответствии с определениями функций с подобными именами, объявленных в заголовке \<ctype.h>. Используются следующие константы:  
  
- **space** (функция [isspace](../standard-library/locale-functions.md#isspace))  
  
- **print** (функция [isprint](../standard-library/locale-functions.md#isprint))  
  
- **cntrl** (функция [iscntrl](../standard-library/locale-functions.md#iscntrl))  
  
- **upper** (функция [isupper](../standard-library/locale-functions.md#isupper))  
  
- **lower** (функция [islower](../standard-library/locale-functions.md#islower))  
  
- **digit** (функция [isdigit](../standard-library/locale-functions.md#isdigit))  
  
- **punct** (функция [ispunct](../standard-library/locale-functions.md#ispunct))  
  
- **xdigit** (функция [isxdigit](../standard-library/locale-functions.md#isxdigit))  
  
- **alpha** (функция [isalpha](../standard-library/locale-functions.md#isalpha))  
  
- **alnum** (функция [isalnum](../standard-library/locale-functions.md#isalnum))  
  
- **graph** (функция [isgraph](../standard-library/locale-functions.md#isgraph))  
  
 Вы можете охарактеризовать комбинацию классификаций, выполняя операцию OR с этими константами. В частности, выражение **alnum** == ( **alpha**``&#124; **digit**\) and **graph** \=\= \( **alnum**``&#124; **punct**) всегда имеет значение true.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)





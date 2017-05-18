---
title: "Структура char_traits&lt;char16_t&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- char_traits<char16_t>
- string/std::char_traits<char16_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: f1bd54744bcb80508b275f530c913ddafbd53c4f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="chartraitsltchar16tgt-struct"></a>Структура char_traits&lt;char16_t&gt;
Структура, которая является специализацией структуры шаблона **char_traits\<CharType>** к элементу типа `char16_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <>  
struct char_traits<char16_t>;
```  
  
## <a name="remarks"></a>Примечания  
 Специализация позволяет структуре использовать преимущества функций библиотеки, которые управляют объектами данного типа `char16_t`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<string>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<string>](../standard-library/string.md)   
 [Структура char_traits](../standard-library/char-traits-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)





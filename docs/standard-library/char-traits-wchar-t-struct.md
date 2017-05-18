---
title: "Структура char_traits&lt;wchar_t&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- char_traits<wchar_t>
- string/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
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
ms.openlocfilehash: 8816f9cadccdb1c8b52733c079668f1b07ea54da
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="chartraitsltwchartgt-struct"></a>Структура char_traits&lt;wchar_t&gt;
Класс, который является специализацией структуры шаблона **char_traits\<CharType>** к элементу типа `wchar_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <>  
struct char_traits<wchar_t>;
```  
  
## <a name="remarks"></a>Примечания  
 Специализация позволяет структуре использовать преимущества функций библиотеки, которые управляют объектами данного типа `wchar_t`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<string>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Структура char_traits](../standard-library/char-traits-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)





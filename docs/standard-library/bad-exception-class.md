---
title: "Класс bad_exception | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.bad_exception
- bad_exception
- std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7870c00b019718188b80a64e0102638deb76f588
ms.lasthandoff: 02/24/2017

---
# <a name="badexception-class"></a>Класс bad_exception
Этот класс описывает исключение, которое может быть вызвано из обработчика unexpected.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Примечания  
 Обработчик [unexpected](../standard-library/exception-functions.md#unexpected) вызовет `bad_exception` вместо завершения или вместо вызова другой функции, указанной с помощью [set_unexpected](../standard-library/exception-functions.md#set_unexpected), если `bad_exception` включен в список throw функции.  
  
 Значение, возвращаемое **what**, — это определяемая в реализации строка C. Ни одна из функций-членов не создает исключение.  
  
 Список членов, наследуемых классом `bad_exception`, см. в разделе [Класс exception](../standard-library/exception-class.md).  
  
## <a name="example"></a>Пример  
 Пример использования [unexpected](../standard-library/exception-functions.md#unexpected), вызывающего `bad_exception`, см. в разделе [set_unexpected](../standard-library/exception-functions.md#set_unexpected).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<exception>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
[Класс exception](../standard-library/exception-class.md)
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



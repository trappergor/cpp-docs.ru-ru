---
title: "Безопасные библиотеки: стандартная библиотека C++ | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 704101f267c1d63ffc5def918f031bfc9b257e67
ms.lasthandoff: 02/24/2017

---
# <a name="safe-libraries-c-standard-library"></a>Безопасные библиотеки: стандартная библиотека C++
В библиотеки, входящие в состав Visual C++ (включая стандартную библиотеку C++), были внесены различные улучшения, чтобы сделать их более безопасными.  
  
 В стандартной библиотеке C++ несколько методов оказались потенциально небезопасными, так как могли привести к переполнению буфера или другим дефектам кода. Использовать эти методы не рекомендуется; вместо них созданы новые, более безопасные методы. Эти новые методы оканчиваются на `_s`.  
  
 Также были внесены некоторые улучшения для повышения безопасности итераторов и алгоритмов. Дополнительные сведения см. в разделах [Проверяемые итераторы](../standard-library/checked-iterators.md), [Поддержка в отладке итераторов](../standard-library/debug-iterator-support.md) и [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице перечислены потенциально небезопасные методы стандартной библиотеки C++, а также их более безопасные эквиваленты:  
  
|Потенциально небезопасный метод|Более безопасный эквивалент|  
|-------------------------------|----------------------|  
|[basic_string::copy](../standard-library/basic-string-class.md#basic_string__copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#basic_string___copy_s)|  
|[char_traits::copy](../standard-library/char-traits-struct.md#char_traits__copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#char_traits___copy_s)|  
  
 При вызове любого из перечисленных выше потенциально небезопасных методов или при неправильном использовании итераторов компилятор создает [Предупреждение компилятора (уровень 3) С4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Сведения о том, как отключить эти предупреждения, см. в разделе [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="in-this-section"></a>Содержание  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Проверяемые итераторы](../standard-library/checked-iterators.md)  
  
 [Поддержка итераторов отладки](../standard-library/debug-iterator-support.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)



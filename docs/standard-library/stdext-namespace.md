---
title: "Пространство имен stdext | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
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
ms.openlocfilehash: 213b760a134a645a0b6552e4c3600fc4762b0bb2
ms.lasthandoff: 02/24/2017

---
# <a name="stdext-namespace"></a>Пространство имен stdext
Члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) в настоящее время не являются частью стандарта ISO C++. Поэтому эти типы и члены были перемещены из пространства имен `std` в пространство имен `stdext`в целях поддержания соответствия стандарту C++.  
  
 При компиляции с параметром [/Ze](../build/reference/za-ze-disable-language-extensions.md), который используется по умолчанию, компилятор выдает предупреждение об использовании `std` для членов файлов заголовков <hash_map> и <hash_set>. Для отключения этого предупреждения используется директива pragma [warning](../preprocessor/warning.md) .  
  
 Чтобы компилятор выдавал ошибку при использовании `std` для членов файлов заголовков <hash_map> и <hash_set> с параметром **/Ze**, добавьте следующую директиву перед включением файлов заголовков стандартной библиотеки C++ с помощью #include.  
  
```  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  
  
 При компиляции с параметром **/Za**компилятор выдаст ошибку.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)



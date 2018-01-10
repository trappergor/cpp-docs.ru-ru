---
title: "Класс vector&lt;bool&gt;::reference | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vector/vector<bool>::reference
dev_langs: C++
helpviewer_keywords: vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ebca8cefef2aa53d2726d734932363d54426247
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="vectorltboolgtreference-class"></a>Класс vector&lt;bool&gt;::reference
Класс `vector<bool>::reference` — это прокси-класс, предоставленный классом [vector\<bool> ](../standard-library/vector-bool-class.md) для моделирования `bool&`.  
  
## <a name="remarks"></a>Примечания  
 Необходима смоделированная ссылка, поскольку C++ изначально не допускает прямых ссылок на биты. `vector<bool>` использует только один бит на элемент, ссылку на который можно создать с помощью данного класса прокси. Однако моделирование ссылки является незавершенным, поскольку определенные назначения не являются допустимыми. Например, следующий пример использования объекта [vector\<bool>::operator[]](http://msdn.microsoft.com/Library/97738633-690d-4069-b2d9-8c54104fbfdd) является неправильным, так как невозможно получить адрес объекта `vector<bool>::reference`.  
  
```cpp  
vector<bool> vb;  
// ...  
bool* pb = &vb[1]; // conversion error - do not use  
bool& refb = vb[1];   // conversion error - do not use  
```  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|Инвертирует логическое значение элемента вектора.|  
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|Обеспечивает неявное преобразование из `vector<bool>::reference` в `bool`.|  
|[оператор=](../standard-library/vector-bool-reference-operator-assign.md)|Присваивает биту логическое значение или значение, которое содержит элемент со ссылкой.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<vector>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [\<vector>](../standard-library/vector.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


---
title: "Класс vector&lt;bool&gt;::reference | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vector<bool>::reference"
  - "std::vector<bool>::reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector<bool> - ссылочный класс"
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
caps.latest.revision: 22
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс vector&lt;bool&gt;::reference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс `vector<bool>::reference` — это прокси\-класс, предоставленный классом [vector\<bool\> для](../Topic/vector%3Cbool%3E%20Class.md) моделирования `bool&`.  
  
## Заметки  
 Необходима смоделированная ссылка, поскольку C\+\+ изначально не допускает прямых ссылок на биты.  `vector<bool>` использует только один бит на элемент, ссылку на который можно создать с помощью данного класса прокси.  Однако моделирование ссылки является незавершенным, поскольку определенные назначения не являются допустимыми.  Например, поскольку невозможно получить адрес объекта `vector<bool>::reference`, следующий код, использующий объект [vector\<bool\>::operator&#91;&#93;](../Topic/vector%3Cbool%3E::operator.md), является неправильным:  
  
```cpp  
    vector<bool> vb;  
...  
    bool* pb = &vb[1]; // conversion error - do not use  
    bool& refb = vb[1];   // conversion error - do not use  
  
```  
  
### Функции\-члены  
  
|||  
|-|-|  
|[flip](../standard-library/vector-bool-reference-flip.md)|Инвертирует логическое значение элемента вектора.|  
|[operator bool](../Topic/vector%3Cbool%3E::reference::operator%20bool.md)|Обеспечивает неявное преобразование из `vector<bool>::reference` в `bool`.|  
|[operator\=](../standard-library/vector-bool-reference-operator-assign.md)|Присваивает биту логическое значение или значение, которое содержит элемент со ссылкой.|  
  
## Требования  
 **Заголовок**: \<vector\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<vector\>](../standard-library/vector.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)
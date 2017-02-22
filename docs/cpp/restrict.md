---
title: "__restrict | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__restrict"
  - "__restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__restrict - ключевое слово [C++]"
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Применяется к объявлению или определению функции, возвращающей тип указателя; сообщает компилятору, что функция возвращает объект, который не будет связываться ни с какими другими указателями.  
  
## Синтаксис  
  
```  
__declspec(restrict) return_type f();  
```  
  
## Заметки  
 Компилятор распространяет `__declspec(restrict)`.  Например, функция среды CRT `malloc` декорируется модификатором `__declspec(restrict)`; поэтому подразумевается, что указатели, инициализированные в расположениях памяти с помощью функции `malloc`, также не будут иметь псевдонимов.  
  
 Компилятор не проверяет, действительно ли указатель не имеет псевдонимов.  Разработчик должен обеспечить, чтобы программа не создавала псевдонимы для указателя, помеченного модификатором `restrict __declspec`.  
  
 Аналогичную семантику для переменных см. в разделе [\_\_restrict](../cpp/extension-restrict.md).  
  
## Пример  
 Пример использования модификатора `restrict` см. в разделе [noalias](../cpp/noalias.md).  
  
 Сведения о ключевом слове restrict, входящем в C\+\+ AMP, см. в разделе [restrict \(C\+\+ AMP\)](../cpp/restrict-cpp-amp.md).  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)
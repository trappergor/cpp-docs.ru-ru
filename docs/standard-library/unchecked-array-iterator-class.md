---
title: "Класс unchecked_array_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unchecked_array_iterator"
  - "stdext::unchecked_array_iterator"
dev_langs: 
  - "C++"
ms.assetid: 693b3b30-4e3a-465b-be06-409700bc50b1
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Класс unchecked_array_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс `unchecked_array_iterator` позволяет заключить массив или указатель в оболочку из непроверенного итератора.  Используйте этот класс в качестве оболочки \(с помощью функции [make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md)\) для необработанных указателей или массивов, как способ целенаправленного выполнения проверки и управления непроверенными предупреждениями об указателях вместо глобального отключения данных предупреждений.  Если возможно, используйте проверенную версию этого класса, [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md).  
  
> [!NOTE]
>  Этот класс является предоставляемым Microsoft расширением стандартной библиотеки C\+\+.  Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.  
  
## Синтаксис  
  
```  
template <class Iterator>  
    class unchecked_array_iterator;  
```  
  
## Заметки  
 Этот класс определяется в пространстве имен [stdext](../Topic/stdext%20Namespace.md).  
  
 Это непроверенная версия [класса checked\_array\_iterator](../standard-library/checked-array-iterator-class.md) и поддерживает те же перегрузки и члены.  Дополнительные сведения о функции проверяемого итератора с примерами кода см. в разделе [Проверяемые итераторы](../standard-library/checked-iterators.md).  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)
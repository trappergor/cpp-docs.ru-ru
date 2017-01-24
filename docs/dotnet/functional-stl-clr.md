---
title: "functional (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/functional> - заголовок [STL/CLR]"
  - "<functional> - заголовок [STL/CLR]"
  - "функциональные функции [STL/CLR]"
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# functional (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Включать заголовок `<cliext/functional>` STL\/CLR для определения нескольких классы\-шаблоны и соответствующих делегатов и функций шаблона.  
  
## Синтаксис  
  
```  
#include <functional>  
```  
  
## Объявления  
  
|Делегат|Описание|  
|-------------|--------------|  
|[binary\_delegate](../Topic/binary_delegate%20\(STL-CLR\).md)|2 — аргумента делегата.|  
|[binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)|2 — возвращения аргумента делегата `void`.|  
|[unary\_delegate](../dotnet/unary-delegate-stl-clr.md)|От аргумента делегата.|  
|[unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)|Делегат от аргумента возвращения `void`.|  
  
|Класс|Описание|  
|-----------|--------------|  
|[binary\_negate](../dotnet/binary-negate-stl-clr.md)|Функтором для отрицания функтором 2 — аргумента.|  
|[binder1st](../dotnet/binder1st-stl-clr.md)|Функтором привязать первый аргумент функтором 2 — аргумента.|  
|[binder2nd](../Topic/binder2nd%20\(STL-CLR\).md)|Функтором для привязки второй аргумент в функтором 2 — аргумента.|  
|[divides](../dotnet/divides-stl-clr.md)|Функтором границы.|  
|[equal\_to](../dotnet/equal-to-stl-clr.md)|Равное функтором сравнения.|  
|[greater](../dotnet/greater-stl-clr.md)|Большие функтором сравнения.|  
|[greater\_equal](../Topic/greater_equal%20\(STL-CLR\).md)|Больше или равное функтором сравнения.|  
|[less](../dotnet/less-stl-clr.md)|Меньше функтором сравнения.|  
|[less\_equal](../dotnet/less-equal-stl-clr.md)|Или равное функтором сравнения.|  
|[logical\_and](../dotnet/logical-and-stl-clr.md)|Логическое И функтором.|  
|[logical\_not](../dotnet/logical-not-stl-clr.md)|Логическое НЕ функтором.|  
|[logical\_or](../Topic/logical_or%20\(STL-CLR\).md)|Логического ИЛИ функтором.|  
|[minus](../dotnet/minus-stl-clr.md)|Вычитание функтором.|  
|[остатка от деления](../dotnet/modulus-stl-clr.md)|Функтором модуля.|  
|[multiplies](../Topic/multiplies%20\(STL-CLR\).md)|Умножьте функтором.|  
|[negate](../Topic/negate%20\(STL-CLR\).md)|Функтором для получения его отрицанный аргумент.|  
|[not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)|Равное функтором сравнения.|  
|[plus](../dotnet/plus-stl-clr.md)|Добавьте функтором.|  
|[unary\_negate](../dotnet/unary-negate-stl-clr.md)|Функтором для отрицания функтором от аргумента.|  
  
|Функция|Описание|  
|-------------|--------------|  
|[bind1st](../dotnet/bind1st-stl-clr.md)|Создает binder1st для аргумента и функтором.|  
|[bind2nd](../dotnet/bind2nd-stl-clr.md)|Создает binder2nd для аргумента и функтором.|  
|[not1](../dotnet/not1-stl-clr.md)|Создает unary\_negate для функтором.|  
|[not1](../dotnet/not1-stl-clr.md)|Создает binary\_negate для функтором.|  
  
## Требования  
 **Заголовок:**\<cliext\/functional\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)
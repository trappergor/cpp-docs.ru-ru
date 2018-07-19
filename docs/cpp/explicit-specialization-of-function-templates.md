---
title: Явная специализация шаблонов функций | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e35eda35a7d2474826ce151292121be224955420
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410737"
---
# <a name="explicit-specialization-of-function-templates"></a>Явная специализация шаблонов функций
Используя шаблон функции, можно указать особое поведение для определенного типа, предоставив явную специализацию (переопределение) шаблона функции для этого типа. Пример:  
  
```cpp
template<> void MySwap(double a, double b);  
```  
  
 Это объявление позволяет определить другую функцию для **двойные** переменных. Подобно функциям, не являющимся шаблоном, стандартные преобразования типов (например, преобразование типа **float** для **двойные**) применяются.  
  
## <a name="example"></a>Пример  
  
```cpp
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Шаблоны функций](../cpp/function-templates.md)

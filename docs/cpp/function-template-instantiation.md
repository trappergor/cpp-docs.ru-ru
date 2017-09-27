---
title: "Создание экземпляра шаблона функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: b7661e152484f9baab10207454538af8ca57f3b8
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="function-template-instantiation"></a>Создание экземпляра шаблона функции
При первом вызове шаблона функции для каждого типа компилятор создает экземпляр. Каждый экземпляр представляет собой шаблонную функцию, специализированную для данного типа. Этот экземпляр будет вызваться каждый раз, когда функция используется для данного типа. Если имеется несколько одинаковых экземпляров, даже в различных модулях, в исполняемый файл будет помещен только один экземпляр.  
  
 В шаблонах функций преобразование аргументов функции разрешается для любых пар аргументов и параметров, в которых параметр не зависит от аргумента шаблона.  
  
 Можно явно создавать экземпляры шаблонов функций, объявляя шаблон с определенным типом в качестве аргумента. Например, приведенный ниже код допустим:  
  
```cpp
// function_template_instantiation.cpp  
template<class T> void f(T) { }  
  
// Instantiate f with the explicitly specified template.  
// argument 'int'  
//  
template void f<int> (int);  
  
// Instantiate f with the deduced template argument 'char'.  
template void f(char);  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Шаблоны функций](../cpp/function-templates.md)


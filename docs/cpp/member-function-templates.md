---
title: "Шаблоны функций-членов | Документы Microsoft"
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
- function templates, member functions
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6d16c94eb9d88f8e000f3830477fbf420acf8b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="member-function-templates"></a>Шаблоны функций-членов

Шаблон элементов терминов относится как к шаблонам функций-членов, так и к шаблонам вложенных классов. Шаблоны функций-членов — это функции-шаблоны, являющиеся членами класса или шаблона класса.  
  
 Функции-члены могут являться функциями-шаблонами в нескольких контекстах. Все функции шаблонов классов являются общими, однако они не являются шаблонами элементов или шаблонами функций-членов. Если такие функции-члены принимают собственные аргументы шаблона, они считаются шаблонами функций-членов.  
  
## <a name="example"></a>Пример

 Шаблоны функции-члена нешаблонных или шаблонных классов объявляются в виде шаблонов функций с собственными шаблонными параметрами.  
  
```cpp
// member_function_templates.cpp  
struct X  
{  
   template <class T> void mf(T* t) {}  
};  
  
int main()  
{  
   int i;  
   X* x = new X();  
   x->mf(&i);  
}  
```  
  
## <a name="example"></a>Пример

 В следующем примере показан шаблон функции-члена шаблонного класса.  
  
```cpp
// member_function_templates2.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u)  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>Пример
  
```cpp
// defining_member_templates_outside_class.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u);  
};  
  
template<typename T> template <typename U>  
void X<T>::mf(const U &u)  
{  
}  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>Пример

 Локальные классы не могут иметь шаблоны элементов.  
  
 Функции шаблонов-элементов не могут быть виртуальными функциями или переопределять виртуальные функции из базового класса, если они объявлены с тем же именем, что и виртуальная функция базового класса.  
  
Ниже приведен пример шаблонного пользовательского преобразования.  
  
```cpp
// templated_user_defined_conversions.cpp  
template <class T>  
struct S  
{  
   template <class U> operator S<U>()  
   {  
      return S<U>();  
   }  
};  
  
int main()  
{  
   S<int> s1;  
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.  
}  
```  
  
## <a name="see-also"></a>См. также

 [Шаблоны функций](../cpp/function-templates.md)

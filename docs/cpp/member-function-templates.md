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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: bba7b35c08fbc171ddbb4c572285c0aed2f58a3b
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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

 Кроме того, в Visual Studio .NET 2003 и более поздних версиях шаблоны элементов можно определить вне класса.  
  
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
  
 Visual C++ .NET 2003 появилась поддержка шаблонные пользовательские преобразования. Следующий пример работает в Visual C++ .NET 2003 в соответствии со стандартом.  
  
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


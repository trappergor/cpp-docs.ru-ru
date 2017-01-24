---
title: "Шаблоны функций-членов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "шаблоны функций, функция-член"
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Шаблоны функций-членов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблон элементов терминов относится как к шаблонам функций\-членов, так и к шаблонам вложенных классов.  Шаблоны функций\-членов — это функции\-шаблоны, являющиеся членами класса или шаблона класса.  Дополнительные сведения см. в разделе [Шаблоны вложенных классов](../Topic/Nested%20Class%20Templates.md).  
  
 Функции\-члены могут являться функциями\-шаблонами в нескольких контекстах.  Все функции шаблонов классов являются общими, однако они не являются шаблонами элементов или шаблонами функций\-членов.  Если такие функции\-члены принимают собственные аргументы шаблона, они считаются шаблонами функций\-членов.  Подробные сведения см. в разделе [Функции\-члены классов шаблонов](../Topic/Member%20Functions%20of%20Template%20Classes.md).  
  
## Пример  
 Шаблоны функции\-члена нешаблонных или шаблонных классов объявляются в виде шаблонов функций с собственными шаблонными параметрами.  
  
```  
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
  
## Пример  
 В следующем примере показан шаблон функции\-члена шаблонного класса.  
  
```  
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
  
## Пример  
 Кроме того, в Visual Studio .NET 2003 и более поздних версиях шаблоны элементов можно определять за пределами класса.  
  
```  
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
  
## Пример  
 Локальные классы не могут иметь шаблоны элементов.  
  
 Функции шаблонов\-элементов не могут быть виртуальными функциями или переопределять виртуальные функции из базового класса, если они объявлены с тем же именем, что и виртуальная функция базового класса.  
  
 В Visual C\+\+ .NET 2003 впервые представлена поддержка пользовательских преобразований на основе шаблонов.  Следующий пример работает в Visual C\+\+ .NET 2003 в соответствии со стандартом.  
  
```  
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
  
## См. также  
 [Шаблоны функций](../cpp/function-templates.md)
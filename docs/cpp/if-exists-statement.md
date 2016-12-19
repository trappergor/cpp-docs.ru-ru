---
title: "Оператор __if_exists | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_exists_cpp"
  - "__if_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_exists - ключевое слово [C++]"
  - "идентификаторы, проверка существования"
  - "символы, проверка существования"
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор __if_exists
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Оператор `__if_exists` проверяет, существует ли указанный идентификатор.  Если идентификатор существует, выполняется определенный блок операторов.  
  
## Синтаксис  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`identifier`|Идентификатор, наличие которого требуется проверить.|  
|`statements`|Один или несколько операторов, которые будут выполнены, если `identifier` существует.|  
  
## Заметки  
  
> [!CAUTION]
>  Для получения самых надежных результатов используйте оператор `__if_exists` при следующих ограничениях.  
  
-   Применяйте оператор `__if_exists` только к простым типам, а не шаблонам.  
  
-   Применяйте оператор `__if_exists` к идентификаторам как внутри, так и вне класса.  Не применяйте оператор `__if_exists` к локальным переменным.  
  
-   Используйте оператор `__if_exists` только в теле функции.  За пределами тела функции оператор `__if_exists` может проверять только полностью определенные типы.  
  
-   При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.  
  
 Дополнением к оператору `__if_exists` является оператор [\_\_if\_not\_exists](../cpp/if-not-exists-statement.md).  
  
## Пример  
 Обратите внимание, что в этом примере используются шаблоны, что не рекомендуется.  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## Output  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## См. также  
 [Инструкции выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Оператор \_\_if\_not\_exists](../cpp/if-not-exists-statement.md)
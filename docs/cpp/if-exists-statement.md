---
title: "оператор __if_exists | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __if_exists_cpp
- __if_exists
dev_langs:
- C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
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
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3d0eaa00abb1f833ef491fc27bfee01790776edb
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="ifexists-statement"></a>Оператор __if_exists
Оператор `__if_exists` проверяет, существует ли указанный идентификатор. Если идентификатор существует, выполняется определенный блок операторов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`identifier`|Идентификатор, наличие которого требуется проверить.|  
|`statements`|Один или несколько операторов для выполнения, если `identifier` существует.|  
  
## <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Для получения самых надежных результатов используйте оператор `__if_exists` при следующих ограничениях.  
  
-   Применяйте оператор `__if_exists` только к простым типам, а не шаблонам.  
  
-   Применяйте оператор `__if_exists` к идентификаторам как внутри, так и вне класса. Не применяйте оператор `__if_exists` к локальным переменным.  
  
-   Используйте оператор `__if_exists` только в теле функции. За пределами тела функции оператор `__if_exists` может проверять только полностью определенные типы.  
  
-   При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.  
  
 Дополнением к `__if_exists` инструкция является [__if_not_exists](../cpp/if-not-exists-statement.md) инструкции.  
  
## <a name="example"></a>Пример  
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
  
## <a name="output"></a>Вывод  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор __if_not_exists](../cpp/if-not-exists-statement.md)

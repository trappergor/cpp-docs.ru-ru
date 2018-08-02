---
title: оператор __if_exists | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac866487c25ee4ce75abbebe9b9f9c2a5e97828
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405948"
---
# <a name="ifexists-statement"></a>Оператор __if_exists
**__If_exists** инструкции проверяет, является ли указанный идентификатор существует. Если идентификатор существует, выполняется определенный блок операторов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|*identifier*|Идентификатор, наличие которого требуется проверить.|  
|*Инструкции*|Один или несколько операторов для выполнения, если *идентификатор* существует.|  
  
## <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Для достижения самых надежных результатов используйте **__if_exists** инструкции с учетом следующих ограничений.  
  
-   Применить **__if_exists** инструкцию, чтобы только простые типы, не шаблоны.  
  
-   Применить **__if_exists** инструкции к идентификаторам как внутри, так и вне класса. Не устанавливайте **__if_exists** инструкции для локальных переменных.  
  
-   Используйте **__if_exists** инструкции только в теле функции. За пределами тела функции **__if_exists** инструкция может проверять только полностью определенные типы.  
  
-   При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.  
  
 Дополнением к **__if_exists** инструкция является [__if_not_exists](../cpp/if-not-exists-statement.md) инструкции.  
  
## <a name="example"></a>Пример  
 Обратите внимание, что в этом примере используются шаблоны, что не рекомендуется.  
  
```cpp 
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
  
```Output  
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
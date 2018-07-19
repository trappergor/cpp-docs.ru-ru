---
title: защищенные (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- protected_cpp
dev_langs:
- C++
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b01c2f9ec4fa48cd2f11bd4176110384c1f8d288
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944188"
---
# <a name="protected-c"></a>protected (C++)
## <a name="syntax"></a>Синтаксис  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## <a name="remarks"></a>Примечания  
 **Защищенные** ключевое слово указывает доступ к членам класса в *список членов* до следующего описателя доступа (**открытый** или **private**) или в конце определения класса. Члены класса, объявленные как **защищенные** может использоваться только следующие:  
  
-   Функции-члены класса, который изначально объявил эти элементы.  
  
-   Дружественные элементы класса, который изначально объявил эти элементы.  
  
-   Классы, производные с использованием открытого или защищенного доступа от класса, который изначально объявил эти элементы.  
  
-   Прямые производные с использованием закрытого доступа классы, которые также имеют закрытый доступ к защищенным элементам.  
  
 Если перед именем базового класса, **защищенные** ключевое слово указывает, что открытые и защищенные члены базового класса являются защищенными элементами из его производных классов.  
  
 Защищенные члены не являются закрытые, как **частного** члены, которые доступны только для членов класса, в котором они объявлены, но они не открытые, как **открытый** члены, которые доступны в Любая функция.  
  
 Защищенные члены, которые также объявлены как **статический** доступны для любой функции другу или члена производного класса. Защищенные члены, которые не объявлены как **статический** доступны друзьям и функции-члены в производном классе только через указатель на ссылку или объект производного класса.  
  
 Дополнительные сведения см. в разделе [friend](../cpp/friend-cpp.md), [открытый](../cpp/public-cpp.md), [частного](../cpp/private-cpp.md)и в таблице членского доступа в [управление доступом к членам класса](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>Специально для /clr  
 В CLR-типах ключевые слова описателя доступа C++ (**открытый**, **частного**, и **защищенные**) может повлиять на видимость типов и методов с точки зрения сборок. Дополнительные сведения см. в разделе [управление доступом к членам](member-access-control-cpp.md).  
  
> [!NOTE]
>  Файлы, скомпилированные с помощью [/LN](../build/reference/ln-create-msil-module.md) не затрагиваются этим поведением. В этом случае все управляемые классы (открытые или закрытые) будут видны.  
  
## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr  
  
## <a name="example"></a>Пример  
  
```cpp 
// keyword_protected.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class X {  
public:  
   void setProtMemb( int i ) { m_protMemb = i; }  
   void Display() { cout << m_protMemb << endl; }  
protected:  
   int  m_protMemb;  
   void Protfunc() { cout << "\nAccess allowed\n"; }  
} x;  
  
class Y : public X {  
public:  
   void useProtfunc() { Protfunc(); }  
} y;  
  
int main() {  
   // x.m_protMemb;         error, m_protMemb is protected  
   x.setProtMemb( 0 );   // OK, uses public access function  
   x.Display();  
   y.setProtMemb( 5 );   // OK, uses public access function  
   y.Display();  
   // x.Protfunc();         error, Protfunc() is protected  
   y.useProtfunc();      // OK, uses public access function  
                        // in derived class  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Управление доступом к членам класса](member-access-control-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
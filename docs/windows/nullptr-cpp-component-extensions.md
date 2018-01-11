---
title: "nullptr (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be7fcc147a5f6f4b96f7bf7dd68376613489946c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nullptr--c-component-extensions"></a>nullptr (расширения компонентов C++)
`nullptr` Ключевое слово представляет *значение указателя null*. Значение пустого указателя показывает, что тип дескриптора объекта, внутреннего указателя или собственного указателя не указывает на объект.  
  
 `nullptr` используется с управляемым или машинным кодом. Компилятор выводит соответствующие, но различные инструкции для управляемых и машинных значений пустых указателей. Сведения об использовании стандартной версии C++ ISO ключевого слова см. в разделе [nullptr](../cpp/nullptr.md).  
  
 Ключевое слово `__nullptr` относится только к системам Microsoft и имеет такое же значение, что и ключевое слово `nullptr`, но применяется только для машинного кода. При использовании `nullptr` с кодом собственного C/C++ и последующей компиляции с [/CLR](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора, компилятор не может определить, является ли `nullptr` указывает значение указателя null машинного или управляемого. Чтобы устранить эту проблему, используйте `nullptr` для указания управляемого значения или `__nullptr`, чтобы указать машинное значение.  
  
 Ключевое слово `nullptr` эквивалентно ключевому слову `Nothing` в Visual Basic и ключевому слову `null` в C#.  
  
## <a name="usage"></a>Использование  
 Ключевое слово `nullptr` можно использовать везде, где может применяться дескриптор, собственный указатель или аргумент функции.  
  
 Ключевое слово `nullptr` не является типом и его использование не поддерживается со следующими элементами:  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr` (хотя `throw (Object^)nullptr;` будет работать)  
  
 Ключевое слово `nullptr` можно применять при инициализации следующих типов указателей:  
  
-   собственного указателя;  
  
-   дескриптора среды выполнения Windows;  
  
-   управляемого дескриптора;  
  
-   управляемого внутреннего указателя.  
  
 Ключевое слово `nullptr` можно использовать для проверки указателя или ссылки дескриптора на значение NULL, прежде чем ссылка будет использоваться.  
  
 Вызовы функций для языков, использующих значения пустых указателей для проверки ошибок, должны правильно интерпретироваться.  
  
 Нельзя инициализировать дескриптор нулем; можно использовать только `nullptr`. При присвоении константы 0 дескриптору объекта создаются упакованный тип `Int32` и приведение к типу `Object^`.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере кода показано, что ключевое слово `nullptr` может использоваться везде, где может применяться дескриптор, собственный указатель или аргумент функции. Также в этом примере показано, что ключевое слово `nullptr` может использоваться для проверки ссылки до ее применения.  
  
```  
// mcpp_nullptr.cpp  
// compile with: /clr  
value class V {};  
ref class G {};  
void f(System::Object ^) {}  
  
int main() {  
// Native pointer.  
   int *pN = nullptr;  
// Managed handle.  
   G ^pG = nullptr;  
   V ^pV1 = nullptr;  
// Managed interior pointer.  
   interior_ptr<V> pV2 = nullptr;  
// Reference checking before using a pointer.  
   if (pN == nullptr) {}  
   if (pG == nullptr) {}  
   if (pV1 == nullptr) {}  
   if (pV2 == nullptr) {}  
// nullptr can be used as a function argument.  
   f(nullptr);   // calls f(System::Object ^)  
}  
```  
  
## <a name="example"></a>Пример  
 **Пример**  
  
 В следующем примере кода показано, что `nullptr` и ноль можно взаимозаменяемо использовать для собственных указателей.  
  
```  
// mcpp_nullptr_1.cpp  
// compile with: /clr  
class MyClass {  
public:  
   int i;  
};  
  
int main() {  
   MyClass * pMyClass = nullptr;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
  
   pMyClass = 0;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
}  
```  
  
 **Вывод**  
  
```Output  
pMyClass == nullptr  
  
pMyClass == 0  
  
pMyClass == nullptr  
  
pMyClass == 0  
```  
  
## <a name="example"></a>Пример  
 **Пример**  
  
 В приведенном ниже примере кода показано, что `nullptr` интерпретируется как дескриптор любого типа или как собственный указатель на любой тип. В случае перегрузки функции с дескрипторами различных типов создается ошибка неоднозначности. `nullptr` необходимо явно приводить к типу.  
  
```  
// mcpp_nullptr_2.cpp  
// compile with: /clr /LD  
void f(int *){}  
void f(int ^){}  
  
void f_null() {  
   f(nullptr);   // C2668  
   // try one of the following lines instead  
   f((int *) nullptr);  
   f((int ^) nullptr);  
}  
```  
  
## <a name="example"></a>Пример  
 **Пример**  
  
 В следующем примере кода показано, что допускается приведение `nullptr`, которое возвращает указатель или дескриптор типа приведения, содержащий значение `nullptr`.  
  
```  
// mcpp_nullptr_3.cpp  
// compile with: /clr /LD  
using namespace System;  
template <typename T>   
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type  
  
int main() {  
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)  
  
   // Delete the following line to resolve.  
   f(nullptr);  
  
   f(0);   // T = int, call f(int)  
}  
```  
  
## <a name="example"></a>Пример  
 **Пример**  
  
 В следующем примере кода показано, что `nullptr` можно использовать в качестве параметра функции.  
  
```  
// mcpp_nullptr_4.cpp  
// compile with: /clr  
using namespace System;  
void f(Object ^ x) {  
   Console::WriteLine("test");  
}  
  
int main() {  
   f(nullptr);  
}  
```  
  
 **Вывод**  
  
```Output  
test  
```  
  
## <a name="example"></a>Пример  
 **Пример**  
  
 В следующем примере кода показано, что, если при объявлении дескрипторов они не инициализируются явно, они по умолчанию инициализируются значением `nullptr`.  
  
```  
// mcpp_nullptr_5.cpp  
// compile with: /clr  
using namespace System;  
ref class MyClass {  
public:  
   void Test() {  
      MyClass ^pMyClass;   // gc type  
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");  
   }  
};  
  
int main() {  
   MyClass ^ x = gcnew MyClass();  
   x -> Test();  
}  
```  
  
 **Вывод**  
  
```Output  
NULL  
```  
  
## <a name="example"></a>Пример  
 **Пример**  
  
 В следующем примере кода показано, что `nullptr` могут быть назначены собственному указателю при компиляции с **/CLR**.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## <a name="requirements"></a>Требования  
 Параметр компилятора: (необязателен; поддерживается всеми параметрами создания кода, включая **/ZW** и **/CLR**)  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)
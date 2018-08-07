---
title: nullptr (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ccfb2b234550f5b7fc03e717d92e74b1fd5d5f74
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604451"
---
# <a name="nullptr--c-component-extensions"></a>nullptr (расширения компонентов C++)
**Nullptr** ключевое слово представляет *значение указателя null*. Значение пустого указателя показывает, что тип дескриптора объекта, внутреннего указателя или собственного указателя не указывает на объект.  
  
 Используйте **nullptr** с управляемым или машинным кодом. Компилятор выводит соответствующие, но различные инструкции для управляемых и машинных значений пустых указателей. Сведения об использовании стандартной версии C++ ISO этого ключевого слова см. в разделе [nullptr](../cpp/nullptr.md).  
  
 **__Nullptr** ключевое слово является ключевым словом характерные для Майкрософт, имеющий то же значение, что **nullptr**, но применяется только для машинного кода. Если вы используете **nullptr** машинного кода C/C++ кода и последующей компиляции с [/CLR](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора, компилятор не может определить ли **nullptr** указывает собственный или управляемые значение пустого указателя. Чтобы сделать снимите флажок, чтобы компилятор, использовать **nullptr** для указания управляемого значения или **__nullptr** для указания собственного значения.  
  
 **Nullptr** ключевое слово эквивалентно **ничего не** в Visual Basic и **null** в C#.  
  
## <a name="usage"></a>Использование  
 **Nullptr** слово может использоваться везде, где можно использовать дескриптор, собственный указатель или аргумент функции.  
  
 **Nullptr** ключевое слово не является типом и не поддерживается для использования с:  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr` (хотя `throw (Object^)nullptr;` будет работать)  
  
 **Nullptr** слово может использоваться при инициализации следующих типов указателей:  
  
-   собственного указателя;  
  
-   дескриптора среды выполнения Windows;  
  
-   управляемого дескриптора;  
  
-   управляемого внутреннего указателя.  
  
 **Nullptr** слово может использоваться для проверки, если указатель или дескриптор ссылка имеет значение null, прежде чем ссылка будет использоваться.  
  
 Вызовы функций для языков, использующих значения пустых указателей для проверки ошибок, должны правильно интерпретироваться.  
  
 Не удалось инициализировать дескриптор нулем; только **nullptr** может использоваться. При присвоении константы 0 дескриптору объекта создаются упакованный тип `Int32` и приведение к типу `Object^`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, что **nullptr** слово может использоваться везде, где дескриптор, собственный указатель или аргумент функции может использоваться. И в примере показывается, **nullptr** слово может использоваться для проверки ссылки до его использования.  
  
```cpp  
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
  
 В следующем примере кода показано, что **nullptr** и ноль можно взаимозаменяемо использовать для собственные указатели.  
  
```cpp  
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
  
 В следующем примере кода показано, что **nullptr** интерпретируется как дескриптор любого типа или как собственный указатель на любой тип. В случае перегрузки функции с дескрипторами различных типов создается ошибка неоднозначности. **Nullptr** пришлось бы быть явно приведен к типу.  
  
```cpp  
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
  
 В следующем примере кода показано, что приведение **nullptr** разрешено и возвращает указатель или дескриптор типа приведения, содержащий **nullptr** значение.  
  
```cpp  
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
  
 В следующем примере кода показано, что **nullptr** можно использовать в качестве параметра функции.  
  
```cpp  
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
  
 В следующем примере кода показано, что если объявлен и не инициализированные явно дескрипторов, они по умолчанию, инициализируется **nullptr**.  
  
```cpp  
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
  
 В следующем примере кода показано, что **nullptr** могут быть назначены собственному указателю при компиляции с параметром `/clr`.  
  
```cpp  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## <a name="requirements"></a>Требования  
 Параметр компилятора: необязателен; поддерживается всеми параметрами создания кода, включая `/ZW` и `/clr`.  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)
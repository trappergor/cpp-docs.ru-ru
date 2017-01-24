---
title: "nullptr (расширения компонентов C++) | Microsoft Docs"
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
  - "__nullptr - ключевое слово (C++)"
  - "nullptr - ключевое слово [C++]"
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nullptr (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `nullptr` представляет *пустой указатель*.  Пустой указатель показывает, что обработчик объекта, тип внутреннего или собственного указателя не указывает на объект.  
  
 `nullptr` используется либо с управляемым, либо с собственным кодом.  Компилятор выводит соответствующие, но различные инструкции для управляемых и собственных значений пустых указателей.  Дополнительные сведения об использовании стандарта ISO C\+\+ версии этого ключевого слова см. в разделе [nullptr](../Topic/nullptr.md).  
  
 Ключевое слово `__nullptr` является специфичным ключевым словом корпорации Microsoft, которое имеет такое же значение, как и `nullptr`, но относится только к собственному коду.  При использовании `nullptr` с собственным кодом C\/C\+\+ C и компилировании с параметром компилятора [\/clr](../build/reference/clr-common-language-runtime-compilation.md), компилятор не может определить, обозначает ли `nullptr` собственное или управляемое значение пустого указателя.  Чтобы сделать запрос понятным для компилятора, используйте `nullptr` для указания управляемого значения или `__nullptr`, чтобы указать собственное значение.  
  
 Ключевое слово `nullptr` эквивалентно ключевому слову `Nothing` в Visual Basic и ключевому слову `null` в C\#.  
  
## Использование  
 Ключевое слово `nullptr` можно использовать везде, где может использоваться дескриптор, собственный указатель или аргумент функции.  
  
 Ключевое слово `nullptr` не является типом и не поддерживается для использования с:  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr` \(хотя `throw (Object^)nullptr;` будет работать\)  
  
 Ключевое слово `nullptr` можно использовать при инициализации следующих типов указателей:  
  
-   Собственный указатель  
  
-   Дескриптор среды выполнения Windows  
  
-   Управляемый дескриптор  
  
-   Управляемый внутренний указатель  
  
 Ключевое слово `nullptr` можно использовать для проверки указателя или ссылки дескриптора на значение NULL, прежде чем ссылка будет использоваться.  
  
 Вызовы функций для языков, использующих значения пустых указателей для проверки ошибок, должны правильно интерпретироваться.  
  
 Нельзя инициализировать дескриптор нулем; можно использовать только `nullptr`.  Присвоение константы 0 дескриптору объекта производит упакованный `Int32` и приведение к типу `Object^`.  
  
## Пример  
 В следующем примере кода показано, что ключевое слово `nullptr` может использоваться везде, где может использоваться дескриптор, собственный указатель или аргумент функции.  Также пример показывает, что ключевое слово `nullptr` может использоваться для проверки ссылки до её использования.  
  
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
  
## Пример  
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
  
 **Output**  
  
  **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**  
 **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**   
## Пример  
 **Пример**  
  
 В следующем примере кода показано, что `nullptr` интерпретируется как дескриптор любого типа или как собственный указатель на любой тип.  В случае перегрузки функции с дескрипторами различных типов создается ошибка неоднозначности.  `nullptr` должен явно приводиться к типу.  
  
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
  
## Пример  
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
  
## Пример  
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
  
 **Output**  
  
  **тест**   
## Пример  
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
  
 **Output**  
  
  **NULL**   
## Пример  
 **Пример**  
  
 В следующем примере кода показано, что `nullptr` можно присвоить собственному указателю при компилировании с параметром **\/clr**.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## Требования  
 Параметр компилятора: \(Не является обязательным; поддерживается всеми параметрами создания кода, включая **\/ZW** и **\/clr**\)  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../Topic/nullptr.md)
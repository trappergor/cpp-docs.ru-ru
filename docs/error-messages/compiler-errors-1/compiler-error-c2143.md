---
title: Ошибка компилятора C2143 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2143
dev_langs:
- C++
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 076f2ccb594edd5d9e627d8a4dcea2d9bb928890
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2143"></a>Ошибка компилятора C2143
Синтаксическая ошибка: отсутствует «токен1» до «токен2»  
  
 Компилятор ожидает особого токена (то есть элемента языка не пробел) и вместо этого находит другой маркер.  
  
 Дополнительные сведения об этой ошибке при она возникает, если вы используете блок try функции, см. [статьи базы знаний 241706](http://support.microsoft.com/kb/241706).  
  
 Проверьте [Справочник по языку C++](../../cpp/cpp-language-reference.md) для определения, где код синтаксически неверен. Поскольку могут возникать ошибки компилятора, после обнаружения строки, которая вызывает проблему, следует проверьте несколько строк кода, вызвавшей ошибку.  
  
 Ошибка C2143 может возникать в различных ситуациях.  
  
 Он может использоваться, когда оператор, который можно указать имя (`::`, `->`, и `.`) следует указать ключевое слово `template`, как показано в этом примере:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 По умолчанию C++ предполагает, что `Ty::PutFuncType` не является шаблоном; таким образом, следующее `<` интерпретируется как меньше-знак "больше".  Необходимо сообщить компилятор явно, `PutFuncType` — это шаблон, чтобы он мог правильно интерпретировать знак угловой скобкой. Чтобы исправить эту ошибку, используйте `template` ключевое слово в зависимом типе имени, как показано ниже:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 Ошибка C2143 может возникать при **/CLR** используется и `using` директива содержит синтаксическую ошибку:  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Он также может возникнуть при попытке скомпилировать файл исходного кода с помощью синтаксиса CLR без параметра **/CLR**:  
  
```cpp  
// C2143b.cpp  
ref struct A {   // C2143 error compile with /clr  
   void Test() {}  
};  
  
int main() {  
   A a;  
   a.Test();  
}  
```  
  
 Первый непробельный символ, следующий `if` инструкция должна быть левая круглая скобка. Компилятор не может преобразовать других действий:  
  
```cpp  
// C2143c.cpp  
int main() {  
   int j = 0;  
  
   // OK  
   if (j < 25)  
      ;  
  
   if (j < 25)   // C2143  
}  
```  
  
 C2143 может возникать при в строке, в котором обнаружена ошибка отсутствует закрывающая фигурная скобка, скобки или точка с запятой или в одной из строк, просто выше:  
  
```cpp  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Или при наличии недопустимый тег в объявлении класса:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Или, если метка не присоединен к оператору. Если необходимо поместить метку самостоятельно, например, в конце составного оператора, присоединить ее к оператором null:  
  
```cpp  
// C2143f.cpp  
// compile with: /c  
void func1() {  
   // OK  
   end1:  
      ;  
  
   end2:   // C2143  
}  
```  
  
 Эта ошибка может возникнуть, когда производится вызов типа в стандартной библиотеке C++:  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 Или отсутствует `typename` ключевое слово:  
  
```cpp  
// C2143h.cpp  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
template <typename T>  
X<T>::Y X<T>::memFunc() {   // C2143  
// try the following line instead  
// typename X<T>::Y X<T>::memFunc() {  
   return Y();  
}  
```  
  
 Или при попытке определить явное создание:  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 В программе на языке C переменные должны быть объявлены в начале функции, и они не могут объявляться после функция выполняет инструкции без объявления.  
  
```C  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
```  

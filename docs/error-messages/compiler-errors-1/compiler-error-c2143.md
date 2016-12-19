---
title: "Ошибка компилятора C2143 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2143"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2143"
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2143
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

синтаксическая ошибка : отсутствует "token1" перед "token2"  
  
 Компилятор ожидает особого токена \(элемента языка, отличного от пробела\), и вместо этого находит другой токен.  
  
 Дополнительные сведения об этой ошибке. она возникает при использовании функция\- блок try см. в разделе [Статья базы знаний 241706](http://support.microsoft.com/kb/241706).  
  
 Чтобы определить места, в которых код синтаксически неверен, см. [Справочник по языку С\+\+](../../cpp/cpp-language-reference.md).  Поскольку компилятор может сообщить об этой ошибке после обнаружения строки, которая вызывает проблему, следует проверить несколько строк кода, находящихся до строки, вызвавшей ошибку.  
  
 Ошибка C2143 может возникать в различных ситуациях.  
  
 Это может произойти, когда оператор, который может содержать имя \(`::`, `->` и `.`\) должен следовать ключевым словом `template`, как показано в следующем примере:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 По умолчанию C\+\+ высказывать `Ty::PutFuncType` не является шаблоном; поэтому следующие `<` интерпретируется как знак "Меньше".  Необходимо сообщить компилятору явно, `PutFuncType` шаблон так, чтобы он мог правильно анализ стенной угольник.  Чтобы устранить эту ошибку, используйте ключевое слово `template` по имени, типа, как показано ниже:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 Ошибка C2143 может возникать при **\/clr** используется и директива `using` содержит синтаксическую ошибку:  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Также может возникнуть при попытке компилировать файл исходного кода с помощью синтаксиса CLR без также с помощью **\/clr**:  
  
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
  
 Первый символ, отличных от Пробела, следующим за выписка `if` должен быть круглой левой скобкой.  Любая другая конструкция не может быть преобразована компилятором:  
  
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
  
 Ошибка C2143 может произойти, если заключительная фигурная скобка, скобки, или точкой с запятой отсутствует линии, в котором обнаружена ошибка или в одной из линий только выше:  
  
```caml  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Или, если недопустимый тег в объявлении класса:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Или, если метка не вложена в инструкцию.  Если необходимо поместить метку саму по себе \(например, в конце составного оператора\), присоедините ее к пустому оператору:  
  
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
  
 Ошибка может возникнуть при неопределенный вызов типа из стандартной библиотеки C\+\+ C:  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 Отсутствует ключевое слово или `typename`:  
  
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
  
 Или при попытке определить явное создание экземпляра, выполните следующие действия.  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 В программе C переменные необходимо объявлять в начале функции; после того, как функция выполняет не связанные с объявлением инструкции, объявлять переменные нельзя.  
  
```c  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
  
```
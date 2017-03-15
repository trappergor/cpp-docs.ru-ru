---
title: "Ошибка компилятора C2065 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 81686df4727ab2b3d5af749174a42016e8443e70
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2065"></a>Ошибка компилятора C2065
identifier: необъявленный идентификатор  
  
 Необходимо указать тип переменной в объявлении, прежде чем ее можно будет использовать. Параметры, которые функция использует, необходимо указать в объявлении (или прототипе) перед использованием функции.  
  
 Возможные причины:  
  
1.  имя идентификатора содержит ошибку;  
  
2.  в идентификаторе используются неверные прописные и строчные буквы;  
  
3.  отсутствует закрывающая кавычка после строковой константы.  
  
4.  При компиляции с отладочной версией среды выполнения C, объявление переменной итератора в стандартной библиотеке C++ `for` цикл и последующая попытка использовать эту переменную итератора выходит за рамки `for` цикла. При компиляции кода стандартной библиотеки C++ с использованием отладочной версии среды выполнения C подразумевается [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  В разделе [поддержку отладки итераторов](../../standard-library/debug-iterator-support.md) подробнее.  
  
5.  Возможно, выполняется вызов функции в файле заголовка SDK, который в настоящее время не поддерживается в среде построения.  
  
6.  Пропущены необходимые файлы включения, особенно при определении `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN` или `WIN32_EXTRA_LEAN`. Эти символы исключают некоторые файлы заголовков из файлов windows.h и afxv_w32.h для ускорения компиляции. (Описание исключаемых файлов см. в файлах windows.h и afxv_w32.h.)  
  
7.  Недопустимое пространство имен. Например, чтобы разрешить функции и операторы стандартной библиотеки C++, которые не являются полными, необходимо указать пространство имен `std` с директивой `using`. При компиляции следующего примера возникает ошибка , так как директива `using` закомментирована, а в пространстве имен `std` задан `cout`:  
  
## <a name="example"></a>Пример  
 В следующем примере показано возникновение ошибки C2065 и приводятся сведения по ее устранению.  
  
```  
// C2065.cpp  
// compile with: /EHsc  
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
   cout << "Hello" << endl;   // C2065  
  
   // Or try the following line instead  
   std::cout << "Hello" << std::endl;  
}  
```  
  
## <a name="example"></a>Пример  
 Если при вызове универсальной функции определить заданный аргумент типа по используемым параметрам не удается, компилятор выдает ошибку. Дополнительные сведения см. в разделе [универсальные функции (C + +/ CLI)](../../windows/generic-functions-cpp-cli.md).  
  
 В следующем примере показано возникновение ошибки C2065 и приводятся сведения по ее устранению.  
  
```  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example"></a>Пример  
 Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: проверка параметров для атрибутов Visual C++.  
  
 В следующем примере показано возникновение ошибки C2065 и приводятся сведения по ее устранению.  
  
```  
// C2065_c.cpp  
// compile with: /c  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```

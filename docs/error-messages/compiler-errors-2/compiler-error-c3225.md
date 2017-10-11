---
title: "Ошибка компилятора C3225 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4cf62ba7b0c3b95f22c27172546ccdd253ed9279
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3225"></a>Ошибка компилятора C3225
Аргумент универсального типа для «аргумент» не может быть «тип», он должен быть типом значения или тип дескриптора  
  
 Аргумент универсального типа не относится к правильному типу.  
  
 Дополнительные сведения см. в разделе [Универсальные типы](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Не удается создать экземпляр универсального типа с собственным типом. Следующий пример приводит к возникновению ошибки C3225.  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере создается компонент с помощью C#. Обратите внимание, что ограничение указывает, что универсального типа можно создать только с типом значения.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## <a name="example"></a>Пример  
 Этот образец использует C#-компонент и нарушается ограничение, которое может быть только экземпляры MyList экземпляр с типом значения, отличного от <xref:System.Nullable>. Следующий пример приводит к возникновению ошибки C3225.  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```

---
title: Ошибка компилятора C3225 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f9f6691ddacf6b3c1347b9fd4cac134433741a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3225"></a>Ошибка компилятора C3225
Аргумент универсального типа для «аргумент» не может быть «тип», он должен быть типом значения или тип дескриптора  
  
 Аргумент универсального типа не относится к правильному типу.  
  
 Дополнительные сведения см. в статье [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).  
  
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
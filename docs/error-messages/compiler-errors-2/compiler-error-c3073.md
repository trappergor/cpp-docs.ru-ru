---
title: Ошибка компилятора C3073 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3073
dev_langs:
- C++
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f565973c386dbaa9c1146756e7ca1b1f75f4b43b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253620"
---
# <a name="compiler-error-c3073"></a>Ошибка компилятора C3073
«Тип»: класс ref не имеет конструктор копии, определяемые пользователем  
  
 В [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) компиляции, компилятор не создает конструктор копии для ссылочного типа. В каком-либо **/CLR** компиляции, необходимо определить вашу собственную копию конструктора для ссылочного типа, если ожидается, что экземпляр типа должен быть скопирован.  
  
 Дополнительные сведения см. в разделе [семантика стека C++ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3073.  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```
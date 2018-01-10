---
title: "Ошибка компилятора C3162 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3162
dev_langs: C++
helpviewer_keywords: C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c3526eecbe125a1a76b637734fecc72785556b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3162"></a>Ошибка компилятора C3162
«Тип»: тип ссылки, имеющий деструктор не может использоваться как тип статические данные-член «член»  
  
 Общеязыковая среда выполнения не знает, когда следует выполнять пользовательский деструктор, если класс также содержит статическую функцию-член.  
  
 Деструктор не будут выполняться, если явно удалить объект.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [/ CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Общие вопросы использования Visual C++ для 64-разрядных систем](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3162.  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```
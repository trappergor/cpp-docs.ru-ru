---
title: "Как: объявление типов значений с использованием ключевого слова interior_ptr (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b42cbbbc175b3d48baa7b7b2e1c1a5b0e4cbf15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>Практическое руководство. Объявление типов значений с использованием ключевого слова interior_ptr (C++/CLI)
`interior_ptr` можно использовать с типом значения.  
  
> [!IMPORTANT]
>  Эта функция языка поддерживается **/CLR** параметр компилятора, а не **/zw** параметр компилятора.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 Следующие C + +/ CLI образце показано, как использовать `interior_ptr` с типом значения.  
  
### <a name="code"></a>Код  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### <a name="output"></a>Вывод  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В типе значения указатель `this` равен interior_ptr.  
  
 В теле нестатической функции-члена типа значения `V` указатель `this` является выражением типа `interior_ptr<V>`. Значение этого выражения — адрес объекта, для которого вызывается эта функция.  
  
### <a name="code"></a>Код  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере показано использование оператора взятия адреса со статическими членами.  
  
 Адрес статического члена типа Visual C++ создает собственный указатель.  Адрес статического члена типа значения является управляемым указателем, так как член типа значения выделяется в куче среды выполнения и может быть перемещен сборщиком мусора.  
  
### <a name="code"></a>Код  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### <a name="output"></a>Вывод  
  
```  
22  
23  
hello  
```  
  
## <a name="see-also"></a>См. также  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)
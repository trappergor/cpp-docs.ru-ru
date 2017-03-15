---
title: "interior_ptr (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "stdcli::language::interior_ptr"
  - "interior_ptr_cpp"
  - "interior_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interior_ptr - зарезервированное слово [C++]"
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interior_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*Внутренний указатель* объявляет указатель внутрь ссылочного типа, но не на сам объект.  Внутренний указатель может указывать на дескриптор ссылки, тип значения, дескриптор упакованного типа, член управляемого типа или на элемент управляемого массива.  
  
## Все среды выполнения  
 \(Отсутствует комментарий для этой функции языка, которая применяется ко всем средам выполнения\).  
  
## среда выполнения Windows  
 \(Отсутствуют комментарии для этой функции языка, которая применяется только в среде выполнения Windows\).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## Среда CLR  
 В следующем примере синтаксиса показан внутренний указатель.  
  
### Синтаксис  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### Параметры  
 *cv\_qualifier*  
 Квалификаторы **const** или `volatile`.  
  
 *type*  
 Тип *initializer*.  
  
 *var*  
 Имя переменной `interior_ptr`.  
  
 *initializer*  
 Элемент ссылочного типа, элемент управляемого массива или любой другой объект, которому может быть присвоен собственный указатель.  
  
### Примечания  
 Собственный указатель не может отслеживать элемент, если его расположение изменилось в управляемой куче, что является результатом перемещения сборщиком мусора экземпляров объекта.  Для того, чтобы указатель правильно ссылался на экземпляр, среде выполнения необходимо обновить указатель на вновь расположенный объект.  
  
 `interior_ptr` представляет надмножество функциональности собственного указателя.  Таким образом, все, что можно присвоить собственному указателю, можно также присвоить `interior_ptr`.  Внутреннему указателю разрешено выполнять тот же набор операций, что и собственному указателю, включая сравнение и вычисления с указателями.  
  
 Внутренний указатель можно объявлять только в стеке.  Внутренний указатель не может быть объявлен как член класса.  
  
 Поскольку внутренние указатели существуют только в стеке, взятие адреса внутреннего указателя вызывает неуправляемый указатель.  
  
 `interior_ptr` неявно преобразуется в `bool`, который позволяет использовать его в условных выражениях.  
  
 Дополнительные сведения об объявлении внутреннего указателя, указывающего на объект, который нельзя переместить в куче со сбором мусора, см. в разделе [pin\_ptr](../Topic/pin_ptr%20\(C++-CLI\).md).  
  
 `interior_ptr` находится в пространстве имен CLI.  Дополнительные сведения см. в разделе [Пространства имен Platform, default и cli](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Дополнительные сведения о внутренних указателях см. в  
  
-   [Практическое руководство. Объявление и использование внутренних указателей и управляемых массивов \(C\+\+\/CLI\)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [Практическое руководство. Объявление типов значений с использованием ключевого слова interior\_ptr \(C\+\+\/CLI\)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [Практическое руководство. Перегрузка функций с внутренними и собственными указателями \(C\+\+\/CLI\)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [Практическое руководство. Объявление внутренних указателей с использованием ключевого слова const \(C\+\+\/CLI\)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере показаны способы объявления и использования внутреннего указателя на ссылочный тип.  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **Output**  
  
 **1**   
**2**   
**3**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)
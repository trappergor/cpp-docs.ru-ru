---
title: "ref new, gcnew (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "gcnew"
  - "ref new"
  - "gcnew_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gcnew - ключевое слово [C++]"
  - "ref new - ключевое слово (C++)"
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ref new, gcnew (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Агрегатное ключевое слово `ref new` выделяет экземпляр типа, который является мусором, собираемым, когда объект становится недоступным, и возвращает дескриптор \([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)\) выделенному объекту.  
  
## Все среды выполнения  
 Память для экземпляра типа, выделяемая `ref new`, освобождается автоматически.  
  
 Операция `ref new` вызывает `OutOfMemoryException`, если не удается выделить память.  
  
 Дополнительные сведения о выделении и освобождении памяти для собственных типов C\+\+ см. в разделе [Операторы new и delete](../cpp/new-and-delete-operators.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Используйте `ref new`, чтобы выделить память для объектов среды выполнения Windows, время существования которых требуется администрировать автоматически.  Объект автоматически освобождается, когда число ссылок становится равным нулю, что происходит после выхода последней копии ссылки за пределы области.  Дополнительные сведения см. в разделе [Классы и структуры ссылки](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Память для управляемого типа \(типа ссылки или значений\) выделяется с помощью `gcnew` и освобождается с помощью сбора мусора.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 **Пример**  
  
 В следующем примере с помощью `gcnew` выделяется объект Message.  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **Пример**  
  
 В следующем примере с помощью `gcnew` создается упакованный тип значения для использования в качестве ссылочного типа.  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **Вывод**  
  
  **32**   
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)
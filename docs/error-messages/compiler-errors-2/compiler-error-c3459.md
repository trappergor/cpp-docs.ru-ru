---
title: "Ошибка компилятора C3459 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3459"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3459"
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3459
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"атрибут": атрибут допустим только в индексаторе класса \(индексированное свойство по умолчанию\)  
  
 Атрибут, создаваемый для применения к свойству индексатора класса, использован неправильно.  
  
 Для получения дополнительной информации см. [Практическое руководство. Использование индексированных свойств](../../misc/how-to-use-indexed-properties.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3459.  
  
```  
// C3459.cpp // compile with: /clr /c public ref class MyString { public: [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459 property int Prop; }; // OK public ref class MyString2 { array<int>^ MyArr; public: MyString2() { MyArr = gcnew array<int>(5); } [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK property int default[int] { int get(int index) { return MyArr[index]; } void set(int index, int value) { MyArr[index] = value; } } };  
```
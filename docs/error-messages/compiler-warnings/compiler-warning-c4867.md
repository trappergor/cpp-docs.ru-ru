---
title: "Предупреждение компилятора C4867 | Microsoft Docs"
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
  - "C4867"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4867"
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4867
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": в вызове функции отсутствует список аргументов; используйте "вызов" для создания указателя на член  
  
 Недопустимая инициализация указателя на функцию\-член.  
  
 Это предупреждение может отображаться в результате выполнения действий по обеспечению расширенной совместимости указателей на члены в Visual C\+\+ 2005.  В текущей версии при компиляции кода, который не содержал ошибок в версиях, предшествующих Visual C\+\+ 2005, возникает предупреждение C4867.  
  
 Это предупреждение всегда выдается как ошибка.  Чтобы отключить это предупреждение, используйте директиву pragma [warning](../../preprocessor/warning.md).  Дополнительные сведения о предупреждении C4867, а также библиотеках MFC и ATL см. в разделе [\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md).  
  
## Пример  
 В следующем примере возникает ошибка C4867.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```
---
title: "Предупреждение компилятора (уровень 4) C4208 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4208"
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение: delete \[exp\] — exp вычислено, но игнорируется  
  
 При использовании расширений Microsoft \(\/Ze\) можно удалить массив с помощью значения в скобках с [оператором удаления](../../cpp/delete-operator-cpp.md).  Значение не обрабатывается.  
  
```  
// C4208.cpp  
// compile with: /W4  
int main()  
{  
   int * MyArray = new int[18];  
   delete [18] MyArray;      // C4208  
   MyArray = new int[18];  
   delete [] MyArray;        // ok  
}  
```  
  
 Данные значения недопустимы в режиме ANSI\-совместимости \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).
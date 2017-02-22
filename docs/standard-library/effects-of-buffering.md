---
title: "Эффекты буферизации | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "буферы, эффекты буферизации"
  - "буферизация, эффекты"
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Эффекты буферизации
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере демонстрируются эффекты буферизации. Вы могли ожидать, что программа выведет `please wait`, подождет 5 секунд и затем продолжит выполнение. Однако такое поведение необязательно, так как выходные данные помещаются в буфер.  
  
```  
// effects_buffering.cpp // compile with: /EHsc #include <iostream> #include <time.h> using namespace std; int main( ) { time_t tm = time( NULL ) + 5; cout << "Please wait..."; while ( time( NULL ) < tm ) ; cout << "\nAll done" << endl; }  
```  
  
 Чтобы программа работала логично, объект `cout` должен опустошать себя перед выводом сообщения. Чтобы сохранить объект `ostream`, отправьте ему манипулятор `flush`:  
  
```  
cout << "Please wait..." << flush;  
```  
  
 Это действие сохраняет буфер, гарантируя вывод сообщения до ожидания. Можно также использовать манипулятор `endl`, который сохраняет буфер и выводит пару "возврат каретки — перевод строки", или использовать объект `cin`. Этот объект \(с объектами `cerr` или `clog`\) обычно привязывается к объекту `cout`. Таким образом, любое использование `cin` \(или объектов `cerr` или `clog`\) сохраняет объект `cout`.  
  
## См. также  
 [Потоки вывода](../standard-library/output-streams.md)
---
title: "Предупреждение компилятора (уровень 1) C4042 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4042"
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Идентификатор": имеет недопустимый класс хранения  
  
 Заданный класс хранения нельзя использовать с этим идентификатором в данном контексте.  Вместо него компилятор использует класс хранения по умолчанию.  
  
-   `extern`, если *идентификатор* является функцией.  
  
-   **авто**, если *идентификатор* является формальным параметром или локальной переменной.  
  
-   Нет класса хранения, если *идентификатор* является глобальной переменной.  
  
 Данное предупреждение может быть вызвано тем, что в объявлении параметра задан класс хранения отличный от **реестра**.  
  
 Следующий пример приводит к возникновению ошибки C4042  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```
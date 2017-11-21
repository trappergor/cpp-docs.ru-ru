---
title: "Предупреждение (уровень 1) C4503 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4503
dev_langs: C++
helpviewer_keywords: C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b174ac92abb0f095895eb587afcba860f4abbe0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4503"></a>Предупреждение компилятора (уровень 1) C4503
«Идентификатор»: длина внутреннего имени превышено, имя усечено  
  
 Внутреннее имя превышает ограничение компилятора (4096) и был усечен. Чтобы избежать этого предупреждения и усечение, уменьшите число аргументов или длина имени идентификаторов, используемых.  
  
 Ситуация, где это предупреждение выдается — Если код содержит шаблоны специализированные для шаблонов.  Например сопоставление схем (стандартная библиотека C++).  В этом случае вы можно определить тип (например, структура), содержащего схему.  
  
 Тем не менее, можно выполнить реструктуризацию кода не.  Можно отправить приложение, создающее C4503, но при появлении ошибки во время ссылку на символ, усеченное, он будет более сложным определить тип символа в сообщении об ошибке.  Отладка также будет более сложным; Отладчик также будет иметь difficultly сопоставление имени символа имени.  Однако правильность программы, не оказывают влияния усеченное имя.  
  
 Следующий пример приводит к возникновению ошибки C4503:  
  
```  
// C4503.cpp  
// compile with: /W1 /EHsc /c  
// C4503 expected  
#include <string>  
#include <map>  
  
class Field{};  
  
typedef std::map<std::string, Field> Screen;  
typedef std::map<std::string, Screen> WebApp;  
typedef std::map<std::string, WebApp> WebAppTest;  
typedef std::map<std::string, WebAppTest> Hello;  
Hello MyWAT;  
```  
  
 Следующий пример показывает один из способов устранения предупреждения C4503 переписать:  
  
```  
// C4503b.cpp  
// compile with: /W1 /EHsc /c  
#include <string>  
#include <map>  
  
class Field{};  
struct Screen2 {  
   std::map<std::string, Field> Element;  
};  
  
struct WebApp2 {  
   std::map<std::string, Screen2> Element;  
};  
  
struct WebAppTest2 {  
   std::map<std::string, WebApp2> Element;  
};  
  
struct Hello2 {  
   std::map<std::string, WebAppTest2> Element;  
};  
  
Hello2 MyWAT2;  
```
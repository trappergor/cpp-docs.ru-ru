---
title: "Предупреждение компилятора (уровень 1) C4503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4503"
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 1) C4503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": длина внутреннего имени объекта в компиляторе превысила максимальное значение, имя усечено  
  
 Длина внутреннего имени превысила установленное для компилятора ограничение \(4096\). Имя усечено.  Чтобы предотвратить возникновение этого предупреждения и усечение имени, уменьшите число аргументов или длину имен используемых идентификаторов.  
  
 Это предупреждение отображается в том случае, если в коде содержатся шаблоны, специализированные для шаблонов.  В качестве примера можно привести схему схем \(в стандартной библиотеке C\+\+\).  В этом случае можно определить тип \(например структуру\), который содержит схему.  
  
 Структуру кода изменять не обязательно.  Выпуск приложений, в которых возникает предупреждение C4503, допускается. Однако при получении ошибок времени компоновки для усеченного символа определить тип этого символа будет сложнее.  Также в этом случае усложняется процесс отладки и сопоставления имен символов и типов.  Программа, в которой используется усеченное имя, по\-прежнему считается правильной.  
  
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
  
 В следующем примере показан один из способов устранения предупреждения C4503:  
  
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
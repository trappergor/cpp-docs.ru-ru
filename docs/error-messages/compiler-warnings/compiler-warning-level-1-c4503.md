---
title: "Предупреждение компилятора (уровень 1) предупреждение C4503 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: f999fcb73860bfd2fabb3484e78f313a32240dee
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4503"></a>Предупреждение компилятора (уровень 1) C4503
«Идентификатор»: длина внутреннего имени превышено, имя усечено  
  
 Внутреннее имя превышает ограничение компилятора (4096) и был усечен. Чтобы избежать этого предупреждения и усечение, уменьшите число аргументов или длина имени идентификаторов, используемых.  
  
 Одна ситуация, где это предупреждение — когда ваш код содержит шаблоны специализированные для шаблонов.  Например сопоставление схем (стандартная библиотека C++).  В этом случае вы можно определить тип (например, структура), который содержит схему.  
  
 Тем не менее, можно выполнить реструктуризацию кода не.  Выпуск приложений, в которых возникает предупреждение C4503 возможна, но при получении ошибки во время связи с усеченное символ, он будет сложнее для определения типа символов в сообщении об ошибке.  Отладка также будет более сложным; Отладчик также будет иметь difficultly сопоставление имени символа имени.  Правильность работы программы, однако не оказывают усеченное имя.  
  
 В следующем примере возникает предупреждение C4503:  
  
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
  
 Ниже приведен пример одним из способов переписывать код и устранения предупреждения C4503:  
  
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

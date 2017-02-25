---
title: "Предупреждение компилятора (уровень 4) C4211 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4211"
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нестандартное расширение: переопределение extern в static  
  
 С расширениями по умолчанию Майкрософт \(\/Ze\) можно переопределить идентификатор `extern` как **static**.  
  
## Пример  
  
```  
// C4211.c  
// compile with: /W4  
extern int i;  
static int i;   // C4211  
  
int main()  
{  
}  
```  
  
 Такие переопределения недействительны для ANSI\-совместимости \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
## См. также  
 [\(NOTINBUILD\)Static Storage\-Class Specifiers](http://msdn.microsoft.com/ru-ru/3ba9289a-a412-4a17-b319-ceb2c087df48)
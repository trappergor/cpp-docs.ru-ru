---
title: "Предупреждение компилятора (уровень 4) C4205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4205"
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение : объявление статической функции в области видимости функции  
  
 При использовании расширений Майкрософт \(\/Ze\) **статические** функции можно объявлять внутри других функций.  Функция при этом будет относиться к глобальной области видимости.  
  
## Пример  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 Подобная инициализация не допускается в режиме совместимости с ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).
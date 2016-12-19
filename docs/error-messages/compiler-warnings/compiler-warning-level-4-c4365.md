---
title: "Предупреждение компилятора (уровень 4) C4365 | Microsoft Docs"
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
  - "C4365"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4365"
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4365
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"операция": преобразование "тип\_1" в "тип\_2", несоответствие типов со знаком и без  
  
 Например, была произведена попытка преобразования значения без знака в значение со знаком.  
  
 Предупреждение C4365 по умолчанию отключено.  Для получения дополнительной информации см. [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
## Пример  
 Следующий пример приводит к появлению предупреждения C4365.  
  
```  
// C4365.cpp  
// compile with: /W4  
#pragma warning(default:4365)  
  
int f(int) { return 0; }  
void Test(size_t i) {}  
  
int main() {  
   unsigned int n = 10;  
   int o = 10;  
   n++;  
   f(n);   // C4365  
   f(o);   // OK  
  
   Test( -19 );   // C4365  
}  
```
---
title: "Предупреждение компилятора (уровень 2) C4244 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4244"
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 2) C4244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"аргумент": преобразование из "типа1" в "тип2", возможна потеря данных  
  
 Тип с плавающей запятой был преобразован в целый тип.  Возможна потеря данных.  
  
 При получении предупреждения C4244 следует либо изменить программу так, чтобы использовались совместимые типы, либо добавить в код определенную логику, гарантирующую, что диапазон возможных значений будет всегда совместимым с используемыми типами.  
  
 Предупреждение C4244 также может возникать на уровнях 3 и 4. Дополнительные сведения см. в разделе [Предупреждение компилятора \(уровеньs 3 and 4\) C4244](../Topic/Compiler%20Warning%20\(levels%203%20and%204\)%20C4244.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4244:  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```
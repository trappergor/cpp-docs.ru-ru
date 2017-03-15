---
title: "Предупреждение компилятора (уровень 1) C4010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4010"
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

однострочный комментарий содержит знак объединения строк  
  
 Однострочный комментарий, введенный с помощью двух косых \( \/\/ \), содержит обратную косую черту \( \\ \), служащую символом продолжения строки.  Компилятор считает следующую строку продолжением предыдущей и обрабатывает ее как комментарий.  
  
 Некоторые основанные на синтаксисе редакторы не указывают строку, сопровождающую символ продолжения строки, как комментарий.  Игнорируйте цветовую маркировку синтаксиса во всех строках, вызывающих эту ошибку.  
  
 Следующий пример приводит к возникновению ошибки C4010:  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```
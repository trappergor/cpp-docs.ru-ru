---
title: "Предупреждение (уровень 1) C4010 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4010
dev_langs: C++
helpviewer_keywords: C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a56adb54c4a4b7123bde706a2b6b8bdcb184775
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4010"></a>Предупреждение (уровень 1) C4010 компилятора
однострочный комментарий содержит знак продолжения строки  
  
 Однострочный комментарий, введенный с / /, содержит обратную косую черту (\\), служащий символ продолжения строки. Компилятор считает следующую строку продолжением и обрабатывает его как комментарий.  
  
 Некоторые синтаксиса направлены редакторы не указывают строку, следующую символ продолжения как комментарий. Пропуск синтаксиса во всех строках, вызывающих эту ошибку.  
  
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
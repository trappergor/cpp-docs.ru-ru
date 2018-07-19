---
title: Предупреждение (уровень 1) C4010 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06ab6307a34887fe2d8a8719e20c31da9728664b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274658"
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
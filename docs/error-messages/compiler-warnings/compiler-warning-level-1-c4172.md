---
title: Компилятора (уровень 1) предупреждение C4172 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4172
dev_langs:
- C++
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 746442638820d0c81144611a678996dc4c8483b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4172"></a>Компилятора (уровень 1) предупреждение C4172
возвращение адреса локальной переменной или временной  
  
 Функция возвращает адрес локальной переменной или временного объекта. Локальные переменные и временные объекты удаляются, когда функция возвращает, поэтому возвращаемый адрес является недопустимым.  
  
 Измените функцию так, чтобы он возвращал адрес локального объекта.  
  
 Следующий пример приводит к возникновению ошибки C4172:  
  
```  
// C4172.cpp  
// compile with: /W1 /LD  
float f = 10;  
  
const double& bar() {  
// try the following line instead  
// const float& bar() {  
   return f;   // C4172  
}  
```
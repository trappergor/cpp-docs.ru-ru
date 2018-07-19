---
title: Предупреждение (уровень 1) C4530 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74804aa3ea0450c08710a5d0818eae67ce9b556e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283329"
---
# <a name="compiler-warning-level-1-c4530"></a>Предупреждение компилятора (уровень 1) C4530
Обработчик исключений C++ используется, но семантика уничтожения объектов не включены. Задайте параметр/EHsc  
  
 Была использована обработка исключений C++, но [/EHsc](../../build/reference/eh-exception-handling-model.md) не был установлен.  
  
 Если параметр/EHsc не включен, объект автоматически сохраняемый во фрейме между функцией throw и функцию, перехватывающей оператор throw, не будут уничтожены. Однако создать объект с автоматического хранения в **повторите** или **перехватывать** блока будут уничтожены.  
  
 Следующий пример приводит к возникновению ошибки C4530:  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Скомпилируйте образец с параметром/EHsc, чтобы устранить это предупреждение.
---
title: Ошибка компилятора C2563 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85a4de195c681ce8d11b789a9aca102629cc2bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228600"
---
# <a name="compiler-error-c2563"></a>Ошибка компилятора C2563
Несоответствие в списке формальных параметров  
  
 Список формальных параметров функции (или указатель на функцию) не соответствует параметрам другой функции (или указателя на функцию-член). В результате не удается выполнить назначение функций или указателей.  
  
 Следующий пример приводит к возникновению ошибки C2563:  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```
---
title: Ошибка компилятора C2153 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2153
dev_langs:
- C++
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6d288434cce1e1584a61040145b07d26defd9dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169729"
---
# <a name="compiler-error-c2153"></a>Ошибка компилятора C2153
шестнадцатеричные константы должны содержать по крайней мере одну шестнадцатеричную цифру  
  
 Шестнадцатеричные константы 0 x 0 X и \x являются недопустимыми. Необходимо выполнить по крайней мере одну шестнадцатеричную цифру x или X.  
  
 Следующий пример приводит к возникновению ошибки C2153:  
  
```  
// C2153.cpp  
int main() {  
   int a= 0x;    // C2153  
   int b= 0xA;   // OK  
}  
```
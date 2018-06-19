---
title: Предупреждение (уровень 4) C4740 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4740
dev_langs:
- C++
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6260a923da9f48b869707480d64f9be13ef7e9c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293313"
---
# <a name="compiler-warning-level-4-c4740"></a>Предупреждение компилятора (уровень 4) C4740
поток в или встроенного ассемблерного кода препятствуют глобальной оптимизации  
  
 При наличии переход в значение "или" Выход из `asm` блок, для этой функции отключается глобальная оптимизация.  
  
 Следующий пример приводит к возникновению ошибки C4740:  
  
```  
// C4740.cpp  
// compile with: /O2 /W4  
// processor: x86  
int main() {  
   __asm jmp tester  
   tester:;  
}  
```
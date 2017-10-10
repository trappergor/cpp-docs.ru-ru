---
title: "Ошибка компилятора C2432 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d89d894738978359fa0cedb9a9da6c4f9781c135
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2432"></a>Ошибка компилятора C2432
Недопустимая ссылка на 16-разрядные данные в «идентификатор»  
  
 16-битный регистр используется как индекс или базовым регистром. Компилятор не поддерживает ссылки на 16-разрядные данные. 16-разрядное регистров не может использоваться как индекс или базовых при компиляции для 32-разрядного кода.  
  
 Следующий пример приводит к возникновению ошибки C2432:  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```

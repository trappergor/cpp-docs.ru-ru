---
title: Ошибка компилятора C2432 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfbadf2c7d53cce799efbd5f10286b31bb3cd3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196939"
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
---
title: Предупреждение (уровень 3) C4159 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4159
dev_langs:
- C++
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 139a21f5fbb7ce279d96f9df8be6008c2f092287
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291675"
---
# <a name="compiler-warning-level-3-c4159"></a>Предупреждение (уровень 3) C4159 компилятора
\#Директива pragma pragma(pop,...): извлечен ранее занесенный в стек идентификатор «идентификатор»  
  
 Исходный код содержит **принудительной** инструкции с идентификатором директивы pragma, за которым следует **pop** инструкции без идентификатора. В результате ***идентификатор*** является использование стека и последующие ***идентификатор*** может привести к непредвиденному поведению.  
  
 Чтобы избежать этого предупреждения, добавьте идентификатор **pop** инструкции. Например:  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```
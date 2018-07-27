---
title: Предупреждение (уровень 1) C4079 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4079
dev_langs:
- C++
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc6c58649c16365d1bbeb22dcf0676947d5d8ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276572"
---
# <a name="compiler-warning-level-1-c4079"></a>Предупреждение (уровень 1) C4079 компилятора
непредвиденный токен "токен"  
  
 Непредвиденная лексема-разделитель в списке аргументов директивы pragma. В оставшейся части директива pragma была пропущена.  
  
 Следующий пример приводит к возникновению ошибки C4079:  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```
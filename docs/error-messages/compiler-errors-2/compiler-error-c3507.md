---
title: Ошибка компилятора C3507 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3507
dev_langs:
- C++
helpviewer_keywords:
- C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 008267fddbd1d83574081d7b257e6627b32a1f58
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3507"></a>Ошибка компилятора C3507
Идентификатор ProgID не может иметь больше 39 знаков «id»; не содержать знаки пунктуации, помимо '.'; и не может начинаться с цифры  
  
 [Progid](../../windows/progid.md) атрибут имеет ограничения на значения, которые может потребоваться.  
  
 Следующий пример приводит к возникновению ошибки C3507:  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```
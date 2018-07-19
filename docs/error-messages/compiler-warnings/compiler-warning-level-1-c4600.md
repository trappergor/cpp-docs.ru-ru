---
title: Предупреждение (уровень 1) C4600 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4600
dev_langs:
- C++
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7866268cffce31467e5306a969e981f310e91ace
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33287518"
---
# <a name="compiler-warning-level-1-c4600"></a>Предупреждение компилятора (уровень 1) C4600
\#Директива pragma «имя макроса»: требуется допустимая строка пустым  
  
 Нельзя указывать пустую строку при передаче или имени макроса с помощью [pop_macro](../../preprocessor/pop-macro.md) или [push_macro](../../preprocessor/push-macro.md).  
  
 Следующий пример приводит к возникновению ошибки C4600:  
  
```  
// C4600.cpp  
// compile with: /W1  
int main()  
{  
   #pragma push_macro("")   // C4600 passing an empty string  
}  
```
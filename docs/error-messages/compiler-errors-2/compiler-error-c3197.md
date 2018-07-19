---
title: Ошибка компилятора C3197 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3197
dev_langs:
- C++
helpviewer_keywords:
- C3197
ms.assetid: 4e385c3b-222e-425c-9612-46e83ed41650
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f362cad07af1192e9a67a7348ad7a0ad2cad354
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250157"
---
# <a name="compiler-error-c3197"></a>Ошибка компилятора C3197
«ключевое_слово»: может использоваться только в определениях  
  
 Ключевое слово было использовано в объявлении, но допустим только в определении.  
  
 Следующий пример приводит к возникновению ошибки C3197:  
  
```  
// C3197.cpp  
// compile with: /clr /c  
ref struct R abstract;   // C3197  
ref struct R abstract {};   // OK  
  
public ref class MyObject;   // C3197  
ref class MyObject;   // OK  
public ref class MyObject {};   // OK  
```
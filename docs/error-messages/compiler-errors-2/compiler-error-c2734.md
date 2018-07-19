---
title: Ошибка компилятора C2734 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2734
dev_langs:
- C++
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fdc5dda82fe7410afc6e8580f3bedd8ddc289ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237363"
---
# <a name="compiler-error-c2734"></a>Ошибка компилятора C2734
«Идентификатор»: объект const необходимо инициализировать, если не extern  
  
 Идентификатор объявлен `const` , но не инициализирован или `extern`.  
  
 Следующий пример приводит к возникновению ошибки C2734:  
  
```  
// C2734.cpp  
const int j;   // C2734  
extern const int i;   // OK, declared as extern  
```
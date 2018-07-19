---
title: Ошибка компилятора C2199 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2199
dev_langs:
- C++
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31164597c9427dc5e915f5a0315d8e2bb7825e8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169014"
---
# <a name="compiler-error-c2199"></a>Ошибка компилятора C2199
Синтаксическая ошибка: найдено "идентификатор (" в глобальной области видимости (требовалось объявление)?  
  
 В указанном контексте возникла синтаксическая ошибка. Возможно, некорректный синтаксис объявления.  
  
 Следующий пример приводит к возникновению ошибки C2199:  
  
```  
// C2199.cpp  
// compile with: /c  
int j = int(1) int(1);   // C2199  
int j = 1;   // OK  
```
---
title: "Ошибка компилятора C2499 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2499
dev_langs: C++
helpviewer_keywords: C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aaf3a8cfc59a2bf4d602fc8c194d034704f7bc69
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2499"></a>Ошибка компилятора C2499
«класс»: класс не может быть базового класса  
  
 Предпринята попытка указать класс, который был определен как базовый класс.  
  
 Следующий пример приводит к возникновению ошибки C2499:  
  
```  
// C2499.cpp  
// compile with: /c  
class CMyClass : public CMyClass {};   // C2499  
class CMyClass{};   // OK  
```
---
title: "Ошибка компилятора C2731 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2731
dev_langs: C++
helpviewer_keywords: C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82a110e7d222a2fe183d0323472a0266e9779771
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2731"></a>Ошибка компилятора C2731
«Идентификатор»: функция не может быть перегружен  
  
 Функции `main`, `WinMain`, `DllMain`, и `LibMain` не могут быть перегружены.  
  
 Следующий пример приводит к возникновению ошибки C2731:  
  
```  
// C2731.cpp  
extern "C" void WinMain(int, char *, char *);  
void WinMain(int, short, char *, char*);   // C2731  
```
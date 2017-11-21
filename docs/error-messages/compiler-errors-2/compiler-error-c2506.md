---
title: "Ошибка компилятора C2506 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2506
dev_langs: C++
helpviewer_keywords: C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 200155978fe12a142519dd79e50cb409e9ea1e54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2506"></a>Ошибка компилятора C2506
«член»: «__declspec(модификатор)» не может применяться к этому символу  
  
 Для статических членов управляемого класса нельзя объявлять на уровне процесса или на уровне домена приложения.  
  
 Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) .  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2506.  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```
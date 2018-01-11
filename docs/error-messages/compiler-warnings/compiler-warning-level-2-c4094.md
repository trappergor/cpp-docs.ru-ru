---
title: "Предупреждение (уровень 2) C4094 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4094
dev_langs: C++
helpviewer_keywords: C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27b2d664996ee3db1c1b505eb8db0346d683ff8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4094"></a>Предупреждение (уровень 2) C4094 компилятора
без тега «лексема» не объявлены символы  
  
 Компилятор обнаружил пустое объявление с помощью непомеченный структуры, объединения или класса. Объявление учитывается.  
  
## <a name="example"></a>Пример  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 Это условие приведет к ошибке в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
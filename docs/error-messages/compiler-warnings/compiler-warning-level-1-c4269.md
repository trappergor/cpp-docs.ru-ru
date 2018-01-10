---
title: "Предупреждение (уровень 1) C4269 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4269
dev_langs: C++
helpviewer_keywords: C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3d276aa5744d457ee987334d65728b1835593ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4269"></a>Предупреждение компилятора (уровень 1) C4269
«Идентификатор»: «const» автоматическое данные, инициализированные конструктором по умолчанию, созданные компилятором, непредсказуемы  
  
 Объект **const** автоматический экземпляр нетривиального класса инициализирован конструктором по умолчанию, созданный компилятором.  
  
## <a name="example"></a>Пример  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 Поскольку экземпляр класса создан в стеке, начальное значение `m_data` может быть любым. Кроме того, поскольку это **const** экземпляра значение `m_data` не может быть изменено.
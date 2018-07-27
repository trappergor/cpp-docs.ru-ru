---
title: Предупреждение (уровень 1) C4269 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e393c657e12f84d3cadfacd469e35e3472a39d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281795"
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
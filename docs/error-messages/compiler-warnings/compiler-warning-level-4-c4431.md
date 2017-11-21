---
title: "Предупреждение (уровень 4) C4431 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4431
dev_langs: C++
helpviewer_keywords: C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f9f18e625059003eb20c289fd6bbd37a6df45ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4431"></a>Предупреждение компилятора (уровень 4) C4431
отсутствует спецификатор типа — предполагается int. Примечание. C++ не поддерживает тип int по умолчанию  
  
 Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: Visual C++ больше не создает нетипизированные идентификаторы как int по умолчанию. Тип идентификатора необходимо указать явно.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4431.  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```
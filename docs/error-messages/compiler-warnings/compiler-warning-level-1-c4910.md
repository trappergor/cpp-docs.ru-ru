---
title: "Предупреждение (уровень 1) C4910 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f758e2e15d5492724e9b819622202831d4e9f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4910"></a>Предупреждение компилятора (уровень 1) C4910
"\<идентификатор >": «__declspec(dllexport)» и «extern» несовместимы при явном создании экземпляра  
  
 Явное создание экземпляра шаблона с именем  *\<идентификатор >* изменено `__declspec(dllexport)` и `extern` ключевые слова. Однако эти ключевые слова являются взаимоисключающими. Ключевое слово `__declspec(dllexport)` означает создание экземпляра класса шаблона, тогда как ключевое слово `extern` не разрешает автоматическое создание экземпляра класса шаблона.  
  
## <a name="see-also"></a>См. также  
 [Явное создание экземпляра](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Общие правила и ограничения](../../cpp/general-rules-and-limitations.md)
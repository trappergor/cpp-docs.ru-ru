---
title: "Ошибка компилятора C3554 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3554
dev_langs: C++
helpviewer_keywords: C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 90f6e8fee5cd5e31489ff3164ce9a8220e840cde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3554"></a>Ошибка компилятора C3554
"decltype" не может объединяться с любыми другими спецификаторами типа  
  
 Нельзя уточнить ключевое слово `decltype()` с помощью какого-либо описателя типа. Например, следующий фрагмент кода приводит к возникновению ошибки C3554.  
  
```  
int x;  
unsigned decltype(x); // C3554  
```
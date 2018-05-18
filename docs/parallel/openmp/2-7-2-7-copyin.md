---
title: 2.7.2.7 copyin | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ee711bfb24e7a2a1cbada1a7e01a243e204f4a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="2727-copyin"></a>2.7.2.7 copyin
**Copyin** предложение предоставляет механизм для назначения то же значение к **threadprivate** переменные для каждого потока выполнения параллельной области группы. Для каждой переменной, указанной в **copyin** копируется предложения, значение переменной в главный поток команды, как если бы путем назначения в частные для потока копии в начале параллельной области. Синтаксис **copyin** предложение является следующим образом:  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 Ограничения, **copyin** предложение, следующим образом:  
  
-   Переменной, указанной в **copyin** предложения необходимо иметь доступный и однозначный оператор присваивания копии.  
  
-   Переменной, указанной в **copyin** предложение должно быть **threadprivate** переменной.
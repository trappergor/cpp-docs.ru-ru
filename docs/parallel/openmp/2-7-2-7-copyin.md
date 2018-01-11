---
title: "2.7.2.7 copyin | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ba09b70b3a3591b1f8b427ac107576cfcac7935
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
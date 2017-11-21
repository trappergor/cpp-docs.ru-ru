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
ms.openlocfilehash: cd296192146e76085e1b987e29a377eb621917ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
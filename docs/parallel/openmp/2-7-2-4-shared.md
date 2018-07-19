---
title: 2.7.2.4 Общие | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1de0e32e16d889acb8f1339d783bc194b3508dda
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695698"
---
# <a name="2724-shared"></a>2.7.2.4 shared
Это предложение использует переменные, которые отображаются в *списка переменной* среди всех потоков в команде. Все потоки в команде доступ к той же области памяти для **общего** переменных.  
  
 Синтаксис **общего** предложение является следующим образом:  
  
```  
shared(variable-list)  
```
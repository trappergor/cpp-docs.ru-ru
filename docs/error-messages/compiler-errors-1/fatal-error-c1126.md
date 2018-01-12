---
title: "Неустранимая ошибка C1126 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1126
dev_langs: C++
helpviewer_keywords: C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: abe40b1813facb9531312e08371fbe769c32c119
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1126"></a>Неустранимая ошибка C1126
«Идентификатор»: автоматическое выделение памяти превышает размер  
  
 Место, выделенное для локальных переменных функции (а также ограниченный объем пространства, используемого компилятором, такие как дополнительные 20 б для изменяемых функций) превышает предел.  
  
 Чтобы исправить эту ошибку, используйте `malloc` или `new` для выделения больших объемов данных.
---
title: "Ошибка вычислителя выражений CXX0045 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0045
dev_langs: C++
helpviewer_keywords:
- CXX0045
- CAN0045
ms.assetid: 32181bc8-e79c-4ad7-a82f-47c62ec06d7d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bb3fa42a32f65ecd463e0585f1fdb25a9623c50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0045"></a>Ошибка вычислителя выражений CXX0045
не является функцией  
  
 Для символа в программе, которая не является именем функции был предоставлен список аргументов.  
  
## <a name="example"></a>Пример  
  
```  
queue( alpha, beta )  
```  
  
 Если `queue` не является функцией.  
  
 Эта ошибка идентична ошибке CAN0045.
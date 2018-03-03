---
title: "3.1.6 функция omp_in_parallel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e5d05af81eb112894ca27a7599c271138893ee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 Функция omp_in_parallel
**Omp_in_parallel** функция возвращает ненулевое значение, если он вызывается в пределах области динамических параллельной области параллельного выполнения; в противном случае возвращается значение 0. Он следующий:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Эта функция возвращает ненулевое значение, если вызвать в пределах области параллельного выполнения, включая вложенные области, которые сериализуются.
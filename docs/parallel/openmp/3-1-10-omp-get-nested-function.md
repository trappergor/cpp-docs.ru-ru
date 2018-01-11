---
title: "3.1.10 функция omp_get_nested | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36b213ee45018e7cc0ccf3a1cb99dcbd640d4457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 Функция omp_get_nested
`omp_get_nested` Функция возвращает ненулевое значение, если включен вложенный параллелизм и 0, если она отключена. Дополнительные сведения о вложенных параллелизма разделе 3.1.9 на странице 40. Он следующий:  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Если реализация не реализует вложенный параллелизм, эта функция всегда возвращает 0.
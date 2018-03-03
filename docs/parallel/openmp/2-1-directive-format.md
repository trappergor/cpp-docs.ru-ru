---
title: "2.1 формат директивы | Документы Microsoft"
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
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3ff4e0078ffd086ce3b62d8927184188f0ebdd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="21-directive-format"></a>2.1 Формат директивы
Синтаксис в директиве OpenMP формально определяется грамматики в [приложении C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)и иногда следующим образом:  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 Каждая директива начинается с **#pragma omp**, чтобы уменьшить вероятность возникновения конфликта с директивы pragma других (отличных от OpenMP или поставщика расширения с OpenMP) с теми же именами. Остальная часть директивы соглашениям стандартов директивы компилятора C и C++. В частности, можно использовать пробелы до и после  **#** , и иногда необходимо использовать пробелы для разделения слов в директиве. Следующие токены предварительной обработки **#pragma omp** подвержены замены макроса.  
  
 Директивы чувствительны к регистру. Порядок, в котором предложения отображаются в директивы не имеет значения. При необходимости, накладываются ограничения, перечисленных в описании каждое предложение, можно повторить предложений директивы. Если *списка переменной* появляется в предложении, его необходимо указать только переменные. Только один *имя директивы* может быть указана директива.  Например следующая директива не допускается:  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 В директиве OpenMP применяется не более одного последующие инструкции, который должен быть структурированный блок.
---
title: "Ошибка вычислителя выражений CXX0064 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0064
dev_langs: C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2edeb05e39c6d2e70cb2c9dde562a89e85921301
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0064"></a>Ошибка вычислителя выражений CXX0064
Невозможно задать точку останова на связанный виртуальная функция-член  
  
 Была задана точка останова виртуальная функция-член через указатель на объект, например:  
  
```  
pClass->vfunc( int );  
```  
  
 Точки останова можно задать для виртуальной функции путем ввода класса, например:  
  
```  
Class::vfunc( int );  
```  
  
 Эта ошибка идентична ошибке CAN0064.
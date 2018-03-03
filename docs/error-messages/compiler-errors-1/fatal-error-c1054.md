---
title: "Неустранимая ошибка C1054 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c39ba89a36791c56c0b71637cac388b28dc372f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1054"></a>Неустранимая ошибка C1054
ограничение компилятора: недопустимая степень вложения инициализаторов  
  
 Код превышает предел уровней вложенности инициализаторов (10 – 15 уровней, в зависимости от сочетания инициализируемого набора типов).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Упростите типы данных, чтобы уменьшить уровень вложенности инициализируемого.  
  
2.  Инициализируйте переменные в отдельных операторах после объявления.
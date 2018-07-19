---
title: Неустранимая ошибка C1054 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9daac4944c57dbf08fe0ebcbc95993a97838585
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198902"
---
# <a name="fatal-error-c1054"></a>Неустранимая ошибка C1054
ограничение компилятора: недопустимая степень вложения инициализаторов  
  
 Код превышает предел уровней вложенности инициализаторов (10 – 15 уровней, в зависимости от сочетания инициализируемого набора типов).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Упростите типы данных, чтобы уменьшить уровень вложенности инициализируемого.  
  
2.  Инициализируйте переменные в отдельных операторах после объявления.
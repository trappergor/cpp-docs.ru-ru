---
title: "Неустранимая ошибка NMAKE U1035 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d7730f882b40c24822cb4b8e2c6a12147cacf2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1035"></a>Неустранимая ошибка NMAKE U1035
Синтаксическая ошибка: ожидается ":" или «=» разделитель  
  
 Либо двоеточие (**:**) или знак равенства (**=**) ожидался.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Двоеточие не соответствует целевой объект.  
  
2.  Двоеточие и без пробела (например, ответ) следует однобуквенный целевого объекта. NMAKE интерпретирует это как обозначение диска.  
  
3.  Правило определения не поставлено двоеточие.  
  
4.  Определение макроса не следуют знак равенства.  
  
5.  Символ после обратной косой черты (**\\**), использованный для переноса команды на новую строку.  
  
6.  Отобразилась строка, которая не соответствует правилам любое правило синтаксиса (NMAKE).  
  
7.  Makefile был отформатирован с помощью текстовых редакторов.
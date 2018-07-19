---
title: Неустранимая ошибка NMAKE U1035 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6bb32f815345b933ad6a65a0c8c1ec8ad59cbe81
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322800"
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
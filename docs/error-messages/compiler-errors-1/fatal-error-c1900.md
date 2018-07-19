---
title: Неустранимая ошибка C1900 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1900
dev_langs:
- C++
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da7cdd5601785f43748ec87d3219f43728536855
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228991"
---
# <a name="fatal-error-c1900"></a>Неустранимая ошибка C1900
Несоответствие между "tool1" версии "number1" и "tool2" версии "number2"  
  
 Средства, запускаемые на разных этапах работы компилятора, не совпадают. ***Число1*** и ***число2*** относятся к датам файлов. Например, на первом проходе внешний сегмент компилятора запускает (c1.dll), а на втором проходе внутренний сегмент компилятора запускает (c2.dll). Даты файлов должны совпадать.  
  
 Чтобы устранить эту проблему, убедитесь, что к Visual Studio применены все обновления. Если проблема сохранится, используйте **программы и компоненты** панели управления Windows для восстановления или переустановки Visual Studio.
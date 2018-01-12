---
title: "Неустранимая ошибка C1900 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1900
dev_langs: C++
helpviewer_keywords: C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7bffc4c0a60b90ca7eb5f71f3457cced3ec64569
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1900"></a>Неустранимая ошибка C1900
Несоответствие между "tool1" версии "number1" и "tool2" версии "number2"  
  
 Средства, запускаемые на разных этапах работы компилятора, не совпадают. ***Число1*** и ***число2*** относятся к датам файлов. Например, на первом проходе внешний сегмент компилятора запускает (c1.dll), а на втором проходе внутренний сегмент компилятора запускает (c2.dll). Даты файлов должны совпадать.  
  
 Чтобы устранить эту проблему, убедитесь, что к Visual Studio применены все обновления. Если проблема сохранится, используйте **программы и компоненты** панели управления Windows для восстановления или переустановки Visual Studio.
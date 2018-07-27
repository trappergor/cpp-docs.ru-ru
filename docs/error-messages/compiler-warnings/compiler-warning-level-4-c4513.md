---
title: Предупреждение (уровень 4) C4513 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4513
dev_langs:
- C++
helpviewer_keywords:
- C4513
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92c3e89204ec30f9c96a5ea03ede5093dd013d0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292900"
---
# <a name="compiler-warning-level-4-c4513"></a>Предупреждение компилятора (уровень 4) C4513
«класс»: не удалось создать деструктор  
  
 Компилятору не удается создать деструктор по умолчанию для данного класса; деструктор не создан. Деструктор находится в базовый класс, который недоступен для производного класса. Если базовый класс имеет закрытый деструктор, сделайте открытый или защищенный.
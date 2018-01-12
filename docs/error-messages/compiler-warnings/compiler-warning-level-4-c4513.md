---
title: "Предупреждение (уровень 4) C4513 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4513
dev_langs: C++
helpviewer_keywords: C4513
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c07828569b789c6035b5ea28d47d7fd026341026
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4513"></a>Предупреждение компилятора (уровень 4) C4513
«класс»: не удалось создать деструктор  
  
 Компилятору не удается создать деструктор по умолчанию для данного класса; деструктор не создан. Деструктор находится в базовый класс, который недоступен для производного класса. Если базовый класс имеет закрытый деструктор, сделайте открытый или защищенный.
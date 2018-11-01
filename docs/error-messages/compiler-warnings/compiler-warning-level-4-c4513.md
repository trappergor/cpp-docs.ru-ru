---
title: Предупреждение компилятора (уровень 4) C4513
ms.date: 11/04/2016
f1_keywords:
- C4513
helpviewer_keywords:
- C4513
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
ms.openlocfilehash: cbde035a988e5f6ac64303b2ed159b885ece8684
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520085"
---
# <a name="compiler-warning-level-4-c4513"></a>Предупреждение компилятора (уровень 4) C4513

«класс»: не удалось создать деструктор

Компилятор не может создать деструктор по умолчанию для данного класса; деструктор не создан. Деструктор находится в базовый класс, который не доступен для производного класса. Если базовый класс имеет закрытый деструктор, сделать открытый или защищенный.
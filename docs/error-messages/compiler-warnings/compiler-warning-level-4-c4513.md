---
title: Предупреждение компилятора (уровень 4) C4513
ms.date: 11/04/2016
f1_keywords:
- C4513
helpviewer_keywords:
- C4513
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
ms.openlocfilehash: cbde035a988e5f6ac64303b2ed159b885ece8684
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221067"
---
# <a name="compiler-warning-level-4-c4513"></a>Предупреждение компилятора (уровень 4) C4513

«класс»: не удалось создать деструктор

Компилятор не может создать деструктор по умолчанию для данного класса; деструктор не создан. Деструктор находится в базовый класс, который не доступен для производного класса. Если базовый класс имеет закрытый деструктор, сделать открытый или защищенный.
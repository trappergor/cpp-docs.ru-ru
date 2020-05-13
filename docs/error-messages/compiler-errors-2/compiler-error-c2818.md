---
title: Ошибка компилятора C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: 00952e55f1b732bd9af3733f5c0ec575a39116fe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202116"
---
# <a name="compiler-error-c2818"></a>Ошибка компилятора C2818

рекурсивное применение перегруженного оператора "operator->" через тип "тип"

Переопределение оператора доступа к членам класса содержит рекурсивную инструкцию `return`. Чтобы переопределить `->` оператор с рекурсией, необходимо переместить рекурсивную подпрограммы в отдельную функцию, вызываемую из функции переопределения операторов.

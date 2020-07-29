---
title: Ошибка компилятора C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: 786a38aca2c3b9674969018d9e5766eed29c358c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212674"
---
# <a name="compiler-error-c2818"></a>Ошибка компилятора C2818

рекурсивное применение перегруженного оператора "operator->" через тип "тип"

Переопределение оператора доступа к членам класса содержит рекурсивную **`return`** инструкцию. Чтобы переопределить `->` оператор с рекурсией, необходимо переместить рекурсивную подпрограммы в отдельную функцию, вызываемую из функции переопределения операторов.

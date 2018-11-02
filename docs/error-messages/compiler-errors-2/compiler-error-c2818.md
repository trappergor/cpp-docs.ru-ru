---
title: Ошибка компилятора C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: f6e33d0e0ee139138df7d8e11357100b3ec3a1a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593444"
---
# <a name="compiler-error-c2818"></a>Ошибка компилятора C2818

Применение перегруженного «operator ->» является рекурсивным через тип «тип»

Переопределение оператора доступа члена класса содержит рекурсивный `return` инструкции. Чтобы переопределить `->` оператор, необходимо переместить рекурсивную подпрограмму в отдельную функцию, которая вызывается из оператора переопределить функцию.
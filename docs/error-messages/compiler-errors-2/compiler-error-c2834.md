---
title: Ошибка компилятора C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: fb4a0e6f3f6ec227b978ae0b7d3864b2134de986
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677608"
---
# <a name="compiler-error-c2834"></a>Ошибка компилятора C2834

«оператор» должен иметь глобальное полное имя

`new` И `delete` операторы привязаны к классу, где они находятся. Разрешение области не может использоваться для выбора версии `new` или `delete` от другого класса. Чтобы реализовать несколько форм `new` или `delete` оператор, создайте версию оператора с дополнительными формальными параметрами.
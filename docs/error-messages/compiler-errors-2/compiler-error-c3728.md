---
title: Ошибка компилятора C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 68aa23843b0470f15f409b6f3b58624f979ccfae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454591"
---
# <a name="compiler-error-c3728"></a>Ошибка компилятора C3728

«событие»: событие не имеет метода raise

Метаданные, созданные с помощью языка, такие как C#, который не позволяет создавать событие вне класса, в котором он был определен, вошло в состав [#using](../../preprocessor/hash-using-directive-cpp.md) директивы и программы Visual C++ с помощью программирования событие.

Чтобы породить событие в программе, разработанных на языке, например C#, необходимо также определить открытый метод, который вызывает событие класса, содержащего событие.
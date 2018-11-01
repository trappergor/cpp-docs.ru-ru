---
title: Ошибка компилятора C3610
ms.date: 11/04/2016
f1_keywords:
- C3610
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
ms.openlocfilehash: 9965e6420171b2ea48c8fb7bacc0a5a37ea2f227
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591066"
---
# <a name="compiler-error-c3610"></a>Ошибка компилятора C3610

«тип_значения»: тип значения должен быть «упакован» перед вызовом метода «метод»

По умолчанию тип значения не в управляемой куче. Перед вызовом методов из классов среды выполнения .NET, такие как `Object`, необходимо переместить тип значения в управляемой куче.

C3610 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.

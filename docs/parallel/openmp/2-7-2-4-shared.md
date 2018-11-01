---
title: 2.7.2.4 shared
ms.date: 11/04/2016
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
ms.openlocfilehash: ae470f4be67fac57146017d3e2791f6f95aa61b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583447"
---
# <a name="2724-shared"></a>2.7.2.4 shared

Это предложение совместно использует переменные, которые отображаются в *списка переменной* среди всех потоков в группе. Все потоки в группе доступ к той же области памяти для **общего** переменные.

Синтаксис **общего** предложение выглядит следующим образом:

```
shared(variable-list)
```
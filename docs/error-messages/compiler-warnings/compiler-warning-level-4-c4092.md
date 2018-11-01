---
title: Компилятор предупреждение (уровень 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: a6949586cf3faa00aafed37a72e58c1b80266cf5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490426"
---
# <a name="compiler-warning-level-4-c4092"></a>Компилятор предупреждение (уровень 4) C4092

sizeof возвращает «unsigned long»

Операнд `sizeof` оператор был очень велик, поэтому `sizeof` возвращается неподписанный **long**. Это предупреждение возникает при использовании расширений Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). В режиме совместимости с ANSI (/Za) результат усекается вместо этого.
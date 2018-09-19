---
title: Предупреждение (уровень 4) C4092 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4092
dev_langs:
- C++
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84aa73120dabd261d54e764d1e0bfe8bc9c561a0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039618"
---
# <a name="compiler-warning-level-4-c4092"></a>Компилятор предупреждение (уровень 4) C4092

sizeof возвращает «unsigned long»

Операнд `sizeof` оператор был очень велик, поэтому `sizeof` возвращается неподписанный **long**. Это предупреждение возникает при использовании расширений Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)). В режиме совместимости с ANSI (/Za) результат усекается вместо этого.
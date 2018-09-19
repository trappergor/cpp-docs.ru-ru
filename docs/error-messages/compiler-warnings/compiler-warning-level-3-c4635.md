---
title: Предупреждение компилятора (уровень 3) C4635 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7651012d4c48d420734a9c6ec2ff051718f82007
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038117"
---
# <a name="compiler-warning-level-3-c4635"></a>Предупреждение компилятора (уровень 3) C4635

Цель комментария XML-документа: неправильно сформированный XML: причина

Компилятор обнаружил проблему с XML-тегами.  Устраните проблему и выполните повторную компиляцию.

Следующий пример приводит к возникновению ошибки C4635:

```
// C4635.cpp
// compile with: /doc /clr /W3 /c
/// <summary>
/// The contents of the folder have changed.
/// <summary/>   // C4635

// try the following line instead
// /// </summary>
public ref class Test {};
```

Обратите внимание, что в результате для данного примера говорится: **Закрывающий тег member не соответствует открывающему тегу summary.**

Проблема в этом примере это закрывающего тега для \<summary > сформирован неправильно, и компилятор не распознает его как \<summary > закрывающего тега.  \<Член > тег внедряется в XDC-файл компилятором в каждой компиляции/doc.  Таким образом, проблема здесь в том, закрывающий тег \</member >, не соответствует предыдущему открывающему тегу, обработанному компилятором (\<summary >.
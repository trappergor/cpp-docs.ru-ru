---
title: Ошибка компилятора C2377 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2377
dev_langs:
- C++
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f3813642503013ecd2ad3be4c01d55f12c837ba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087044"
---
# <a name="compiler-error-c2377"></a>Ошибка компилятора C2377

"идентификатор": переопределение; typedef нельзя перегрузить с другим символом

Идентификатор `typedef` переопределяется.

В следующем примере возникает ошибка C2377:

```
// C2377.cpp
// compile with: /c
typedef int i;
int i;   // C2377
int j;   // OK
```
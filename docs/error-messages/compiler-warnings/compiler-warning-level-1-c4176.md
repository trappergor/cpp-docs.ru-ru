---
title: Предупреждение компилятора (уровень 1) C4176 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4176
dev_langs:
- C++
helpviewer_keywords:
- C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f173e132a2bd0d54c32fb0c2f7ae3b13dff1657d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085710"
---
# <a name="compiler-warning-level-1-c4176"></a>Предупреждение компилятора (уровень 1) C4176

"подкомпонент": неизвестный компонент для директивы #pragma component browser

Директива pragma **component** содержит недопустимый подкомпонент. Чтобы исключить ссылки на определенное имя, необходимо использовать параметр **references** перед именем.

## <a name="example"></a>Пример

```
// C4176.cpp
// compile with: /W1 /LD
#pragma component(browser, off, i)  // C4176
#pragma component(browser, off, references, i) // ok
```
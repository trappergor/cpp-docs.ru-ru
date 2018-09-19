---
title: Предупреждение компилятора (уровень 4) C4235 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9e709017e51101efe53a8697bb145014f200871
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031825"
---
# <a name="compiler-warning-level-4-c4235"></a>Предупреждение компилятора (уровень 4) C4235

использовано нестандартное расширение: «ключевое слово» не поддерживается в этой архитектуре

Компилятор не поддерживает ключевое слово, которое вы использовали.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4235 предупреждение уровня 2, используйте следующую строку кода

```
#pragma warning(2:4235)
```

в файле исходного кода.
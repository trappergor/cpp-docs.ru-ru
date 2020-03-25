---
title: Предупреждение компилятора (уровень 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: c27f16f7d2933ca1860b304afa6e04f96f0687f0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173911"
---
# <a name="compiler-warning-level-4-c4234"></a>Предупреждение компилятора (уровень 4) C4234

использовано нестандартное расширение: ключевое слово "keyword" зарезервировано для будущего использования

Компилятор еще не реализует ключевое слово, которое вы использовали.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma предупреждение](../../preprocessor/warning.md). Например, чтобы сделать C4234 проблемой с предупреждением уровня 4,

```cpp
#pragma warning(2:4234)
```

в файле исходного кода.

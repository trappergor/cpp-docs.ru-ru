---
title: Предупреждение компилятора C4577
description: Предупреждение компилятора C4577 описание и решение.
ms.date: 09/18/2019
f1_keywords:
- C4577
helpviewer_keywords:
- C4577
ms.openlocfilehash: fb9d412196e7764326a397a4bf6e76c8723ac2ae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196257"
---
# <a name="compiler-warning-level-1-c4577"></a>Предупреждение компилятора (уровень 1) C4577

> "EXCEPT" используется без указания режима обработки исключений; завершение в исключении не гарантируется. Укажите/EHsc

Компилятор обнаружил **`noexcept`** спецификацию, но не задана стандартная обработка исключений C++. Компилятор не полностью поддерживает обработку исключений в соответствии со стандартом C++, если не указан параметр компилятора [/EHsc](../../build/reference/eh-exception-handling-model.md) . Чтобы устранить эту проблему, задайте параметр компилятора **/EHsc** .

Это предупреждение является новым в Visual Studio 2015 и отключено по умолчанию. Дополнительные сведения см. [в разделе предупреждения компилятора, которые по умолчанию отключены](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

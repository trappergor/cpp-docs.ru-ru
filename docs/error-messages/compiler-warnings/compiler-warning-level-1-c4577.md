---
title: Предупреждение компилятора C4577
description: Предупреждение компилятора C4577 описание и решение.
ms.date: 09/18/2019
f1_keywords:
- C4577
helpviewer_keywords:
- C4577
ms.openlocfilehash: e29e47b2a268d86f7f6a280b79a1604fe6eff8a4
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810555"
---
# <a name="compiler-warning-level-1-c4577"></a>Предупреждение компилятора (уровень 1) C4577

> "EXCEPT" используется без указания режима обработки исключений; завершение в исключении не гарантируется. Укажите/EHsc

Компилятор обнаружил спецификацию `noexcept`, но не задана стандартная C++ обработка исключений. Компилятор не полностью поддерживает обработку исключений в соответствии со C++ стандартом, если не указан параметр компилятора [/EHsc](../../build/reference/eh-exception-handling-model.md) . Чтобы устранить эту проблему, задайте параметр компилятора **/EHsc** .

Это предупреждение является новым в Visual Studio 2015 и отключено по умолчанию. Дополнительные сведения см. [в разделе предупреждения компилятора, которые по умолчанию отключены](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

---
title: Ошибка компилятора C3715
ms.date: 11/04/2016
f1_keywords:
- C3715
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
ms.openlocfilehash: 94a451bbe936507ac3b33747065a9b6aac9edd02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660620"
---
# <a name="compiler-error-c3715"></a>Ошибка компилятора C3715

«указатель»: должен быть указателем на «class»

Задан указатель в [__hook](../../cpp/hook.md) или [__unhook](../../cpp/unhook.md) , не указывающий на допустимый класс. Чтобы устранить эту ошибку, убедитесь, что ваш `__hook` и `__unhook` вызовы задают указатели на допустимых классов.
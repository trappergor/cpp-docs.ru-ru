---
title: Ошибка компилятора C3715
ms.date: 11/04/2016
f1_keywords:
- C3715
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
ms.openlocfilehash: c3aff142215286a94a261a1f0fcb411296b57d5a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230783"
---
# <a name="compiler-error-c3715"></a>Ошибка компилятора C3715

"указатель": должен быть указателем на "class"

Вы указали указатель в [`__hook`](../../cpp/hook.md) или [`__unhook`](../../cpp/unhook.md) , который не указывает на допустимый класс. Чтобы устранить эту ошибку, убедитесь, что **`__hook`** **`__unhook`** вызовы и указывают указатели на допустимые классы.

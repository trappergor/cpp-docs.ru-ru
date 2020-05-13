---
title: Ошибка компилятора C3715
ms.date: 11/04/2016
f1_keywords:
- C3715
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
ms.openlocfilehash: 13befc17b94fdf2c22cb84bc64ed55b9375b3473
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165916"
---
# <a name="compiler-error-c3715"></a>Ошибка компилятора C3715

"указатель": должен быть указателем на "class"

Вы указали указатель в [__hook](../../cpp/hook.md) или [__unhook](../../cpp/unhook.md) , который не указывает на допустимый класс. Чтобы устранить эту ошибку, убедитесь, что `__hook` и `__unhook` вызовы указывают указатели на допустимые классы.

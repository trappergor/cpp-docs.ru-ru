---
title: Ошибка компилятора C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: a6a7bc0591fd51c808c303e94eeaaffd6111ffcd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201933"
---
# <a name="compiler-error-c2834"></a>Ошибка компилятора C2834

"operator оператор" должен быть глобально полным

Операторы `new` и `delete` привязаны к классу, где они находятся. Разрешение области нельзя использовать для выбора версии `new` или `delete` из другого класса. Чтобы реализовать несколько форм оператора `new` или `delete`, создайте версию оператора с дополнительными формальными параметрами.

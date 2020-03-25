---
title: Предупреждение компилятора (уровень 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 72ab87b34e07717112f5af1727a216b4f786ae0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186794"
---
# <a name="compiler-warning-level-1-c4420"></a>Предупреждение компилятора (уровень 1) C4420

"оператор": оператор недоступен, вместо него используется оператор "operator"; Проверка во время выполнения может быть нарушена

Это предупреждение создается при использовании [/рткв](../../build/reference/rtc-run-time-error-checks.md) (Проверка создания или удаления вектора) и при отсутствии векторной формы. В этом случае используется невекторная форма.

Чтобы/Рткв правильно работать, компилятор должен всегда вызывать векторную форму [нового](../../cpp/new-operator-cpp.md)/[Delete](../../cpp/delete-operator-cpp.md) , если использовался синтаксис Vector.

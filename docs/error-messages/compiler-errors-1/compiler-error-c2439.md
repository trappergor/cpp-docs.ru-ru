---
title: Ошибка компилятора C2439 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2439
dev_langs:
- C++
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 419bf7be45a1383135d0231cd059837e1fe62729
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058417"
---
# <a name="compiler-error-c2439"></a>Ошибка компилятора C2439

«Идентификатор»: не удалось инициализировать член

Не удается инициализировать класса, структуры или члена объединения.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Попробуйте инициализировать косвенный базовый класс или структура.

1. Попытка инициализировать наследуемый член класса или структуры. Наследуемого члена должны инициализироваться с помощью конструктора класса или структуры.
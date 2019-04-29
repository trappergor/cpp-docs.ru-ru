---
title: Ошибка компилятора C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: f71112d3f37f3e4d1a4f41bade95726d7aa0a0bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311739"
---
# <a name="compiler-error-c2439"></a>Ошибка компилятора C2439

«Идентификатор»: не удалось инициализировать член

Не удается инициализировать класса, структуры или члена объединения.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Попробуйте инициализировать косвенный базовый класс или структура.

1. Попытка инициализировать наследуемый член класса или структуры. Наследуемого члена должны инициализироваться с помощью конструктора класса или структуры.
---
title: Ошибка компилятора C2585 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ec7b1e9c1e5e7894740cc80f9c030fa1ee26ec0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028848"
---
# <a name="compiler-error-c2585"></a>Ошибка компилятора C2585

явное преобразование в «тип» является неоднозначным

Преобразование типов может иметь несколько результатов.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Преобразование из типа класса или структуры на основе множественного наследования. Если тип наследует более одного раза для одного базового класса, функция или оператор преобразования необходимо использовать разрешение области (`::`) чтобы указать, какие из этих классов для использования при преобразовании.

1. Оператор преобразования и конструктор определено сделать то же самое преобразование.
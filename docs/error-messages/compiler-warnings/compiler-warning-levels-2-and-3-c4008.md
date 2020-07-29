---
title: Предупреждение компилятора (уровни 2 и 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: ab51b16331cc6a102c828234d2c2b8be84f2d276
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225245"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Предупреждение компилятора (уровни 2 и 3) C4008

"идентификатор": атрибут "атрибут" игнорируется

Компилятор игнорирует **`__fastcall`** **`static`** атрибут, или **`inline`** для функции (предупреждение уровня 3) или данные (предупреждение уровня 2).

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. **`__fastcall`** атрибут с данными.

1. **`static`****`inline`** атрибут или с функцией **Main** .

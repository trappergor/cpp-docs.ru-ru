---
title: Предупреждение компилятора (уровни 2 и 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 99b78e1426cf1618e68ae74ae7e16dd0f08606ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604091"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Предупреждение компилятора (уровни 2 и 3) C4008

"идентификатор": атрибут "атрибут" игнорируется

Компилятор игнорировал атрибут `__fastcall`, **static**или **inline** для функции (предупреждение уровня 3) или данных (предупреждение уровня 2).

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Атрибут`__fastcall` с данными.

1. Атрибут**static** или **inline** с функцией **main** .
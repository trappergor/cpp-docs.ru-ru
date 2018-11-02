---
title: Неустранимая ошибка NMAKE U1100
ms.date: 11/04/2016
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: a1474acab4ca4929fb4db4b7b78d7a96637a0745
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666600"
---
# <a name="nmake-fatal-error-u1100"></a>Неустранимая ошибка NMAKE U1100

макрос «имя_макроса» является недопустимым в контексте пакетного правила «правило»

NMAKE создает эту ошибку, если блок команд правила пакетного режима прямо или косвенно ссылается на макрос специальный файл, который не является $<.

$< является единственным допустимым макрос для правила пакетного режима.
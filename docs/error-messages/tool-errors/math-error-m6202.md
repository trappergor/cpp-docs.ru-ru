---
title: Математическая ошибка M6202
ms.date: 11/04/2016
f1_keywords:
- M6202
helpviewer_keywords:
- M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
ms.openlocfilehash: c216c4d01513868dd56f47c7d5ca7f8b734d1797
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538571"
---
# <a name="math-error-m6202"></a>Математическая ошибка M6202

«функция»: ошибка _Однотрубный

Аргумент для данной функции является значением сингулярности для этой функции. Функция не определена для этого аргумента.

Эта ошибка вызывает `_matherr` функцию с именем функции, аргументы и тип ошибки. Можно переписать `_matherr` функции для обработки определенных ошибок времени выполнения вычисления с плавающей запятой.
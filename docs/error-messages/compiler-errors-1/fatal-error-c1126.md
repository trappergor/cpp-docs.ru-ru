---
title: Неустранимая ошибка C1126
ms.date: 11/04/2016
f1_keywords:
- C1126
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
ms.openlocfilehash: 3f4d152163d3b21ddf99644c34e63f35ca15e6e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457785"
---
# <a name="fatal-error-c1126"></a>Неустранимая ошибка C1126

«Идентификатор»: автоматическое выделение памяти превышает размер

Пространство, выделенное для локальных переменных функции (а также ограниченное пространство, используемое компилятором, такие как дополнительные 20 б для изменяемых функций) превышает предел.

Чтобы исправить эту ошибку, используйте `malloc` или `new` выделить большие объемы данных.
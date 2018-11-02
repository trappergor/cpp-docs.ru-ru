---
title: Неустранимая ошибка C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: 0bfd0c03378b1a9c616a014ac96153b3ab04af9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569217"
---
# <a name="fatal-error-c1054"></a>Неустранимая ошибка C1054

ограничение компилятора: недопустимая степень вложения инициализаторов

Код превышает предел уровней вложенности инициализаторов (10 – 15 уровней, в зависимости от сочетания типов инициализируемого).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Упростите типы данных, инициализируемого чтобы уменьшить уровень вложенности.

1. Инициализируйте переменные в отдельных инструкциях после объявления.
---
title: Неустранимая ошибка C1054 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 439019b1f510127ae54e77d445d59e86be09a49b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101973"
---
# <a name="fatal-error-c1054"></a>Неустранимая ошибка C1054

ограничение компилятора: недопустимая степень вложения инициализаторов

Код превышает предел уровней вложенности инициализаторов (10 – 15 уровней, в зависимости от сочетания типов инициализируемого).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Упростите типы данных, инициализируемого чтобы уменьшить уровень вложенности.

1. Инициализируйте переменные в отдельных инструкциях после объявления.
---
title: Неустранимая ошибка C1026 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1026
dev_langs:
- C++
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db9167383df48dad274ef8941defaa53f51d3bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068992"
---
# <a name="fatal-error-c1026"></a>Неустранимая ошибка C1026

переполнение стека синтаксического анализатора, слишком сложная программа

Пространство, необходимое для синтаксического анализа программы вызывает переполнение стека компилятора.

Упрощение написания выражения, по:

- Уменьшите уровень вложения `for` и `switch` инструкций. Размещения более глубоко вложенных операторов в отдельных функциях.

- Разбейте длинные выражения, включающие разделителями операторов и вызовов функций.
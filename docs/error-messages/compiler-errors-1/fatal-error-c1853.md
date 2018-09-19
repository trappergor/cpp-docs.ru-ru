---
title: Неустранимая ошибка C1853 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 016e5bbf064643ddff0f63c5e16a967ed914f3e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044955"
---
# <a name="fatal-error-c1853"></a>Неустранимая ошибка C1853

> "*filename*" предкомпилированного файла заголовка с предыдущей версии компилятора или предкомпилированный заголовок является C++ и вы используете его из C (или наоборот)

Возможные причины:

- Предкомпилированный заголовок был скомпилирован с помощью предыдущей версии компилятора. Попробуйте перекомпилировать заголовок с текущим компилятором.

- Предкомпилированный заголовок является C++ и его использовании в C. Попробуйте перекомпилировать заголовок для использования в C, указав одно из [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) параметры компилятора, или измените суффикс исходного файла на «c». Дополнительные сведения см. в разделе [два варианта предварительной компиляции кода](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).
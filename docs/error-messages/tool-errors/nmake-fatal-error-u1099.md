---
title: Неустранимая ошибка NMAKE U1099 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3ef75a1435d8c922087fcdd21d1941961bc82cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113387"
---
# <a name="nmake-fatal-error-u1099"></a>Неустранимая ошибка NMAKE U1099

переполнение стека

Обрабатываемый makefile слишком сложен для текущего выделения стека (NMAKE). NMAKE имеет выделение 0x3000 (12 КБ).

Чтобы увеличить выделение стека NMAKE, запустите [editbin/stack](../../build/reference/stack.md) программы с большим параметром стека:

**EDITBIN/Stack: reserve (NMAKE). EXE-ФАЙЛА**

где *зарезервировать* является числом больше, чем текущее выделение стека (NMAKE).
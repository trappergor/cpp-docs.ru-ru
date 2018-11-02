---
title: Неустранимая ошибка NMAKE U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: 395f25d8d27bc5e9b6132c87390c8c3bc19b6cc4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631222"
---
# <a name="nmake-fatal-error-u1099"></a>Неустранимая ошибка NMAKE U1099

переполнение стека

Обрабатываемый makefile слишком сложен для текущего выделения стека (NMAKE). NMAKE имеет выделение 0x3000 (12 КБ).

Чтобы увеличить выделение стека NMAKE, запустите [editbin/stack](../../build/reference/stack.md) программы с большим параметром стека:

**EDITBIN/Stack: reserve (NMAKE). EXE-ФАЙЛА**

где *зарезервировать* является числом больше, чем текущее выделение стека (NMAKE).
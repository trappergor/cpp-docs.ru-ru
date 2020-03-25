---
title: Неустранимая ошибка NMAKE U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: c963180059a48d9aa0b09103df1ed54f82b8a2f1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193398"
---
# <a name="nmake-fatal-error-u1099"></a>Неустранимая ошибка NMAKE U1099

переполнение стека

Обрабатываемый файл makefile слишком сложен для текущего выделения стека в NMAKE. NMAKE имеет выделение 0x3000 (12K).

Чтобы увеличить выделение стека NMAKE, запустите служебную программу [EDITBIN/Stack](../../build/reference/stack.md) с большим параметром стека:

**EDITBIN/STACK: Reserve NMAKE. ПРОГРАММЫ**

где *Reserve* — это число, большее, чем текущее выделение стека в NMAKE.

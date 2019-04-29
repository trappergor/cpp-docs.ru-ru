---
title: Предупреждение компилятора C4962
ms.date: 11/04/2016
f1_keywords:
- C4962
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
ms.openlocfilehash: e3f7b715da3774d8289fdd526cf1fa0b5bdddba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280806"
---
# <a name="compiler-warning-c4962"></a>Предупреждение компилятора C4962

«функция»: Профильная оптимизация отключена, поскольку операции оптимизации приводят к несогласованности данных профиля»

Функция не была скомпилирована с параметром /LTCG: PGO, так как данные count (profile) для этой функции были недостоверными. Повторите профилирование, чтобы повторно создать PGC-файл, который содержит недостоверные данные профиля для этой функции.

Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).
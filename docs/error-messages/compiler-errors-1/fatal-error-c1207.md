---
title: Неустранимая ошибка C1207 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1207
dev_langs:
- C++
helpviewer_keywords:
- C1207
ms.assetid: cd31b410-9523-47db-883c-e69a9351ffa2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8042782477b402f2e09d1d67c8fd5c126647285
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072632"
---
# <a name="fatal-error-c1207"></a>Неустранимая ошибка C1207

Управляемые шаблоны не поддерживаются установленной версией среды выполнения

Ошибка C1207 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.

Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.

Чтобы устранить ошибку C1207, следует установить версию среды CLR, предназначенную для использования с компилятором.
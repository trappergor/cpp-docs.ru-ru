---
title: Неустранимая ошибка C1208 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1208
dev_langs:
- C++
helpviewer_keywords:
- C1208
ms.assetid: 4eefd8f0-5c2e-4a11-9e63-293e1139db65
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab70449232c7177a555700b96d4965c617692e1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023572"
---
# <a name="fatal-error-c1208"></a>Неустранимая ошибка C1208

Выделение ссылочных классов в стеке не поддерживается установленной версией среды выполнения

Ошибка C1208 возникает, когда компилятор из текущего выпуска используется со средой CLR из предыдущего выпуска.

Некоторые функциональные возможности компилятора могут не работать в предыдущей версии среды выполнения.

Установите версию среды CLR, предназначенную для использования с вашим компилятором.
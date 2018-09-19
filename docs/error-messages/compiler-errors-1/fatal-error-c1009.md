---
title: Неустранимая ошибка C1009 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1009
dev_langs:
- C++
helpviewer_keywords:
- C1009
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1fbd8994be6fd86a764db400d8761a5d697079b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037337"
---
# <a name="fatal-error-c1009"></a>Неустранимая ошибка C1009

ограничение компилятора: недопустимая степень вложения макросы

Компилятор попытался разверните слишком много макросы в то же время. Компилятор имеет ограничение в 256 уровней вложенных макросов. Разбейте макросы на более простые.
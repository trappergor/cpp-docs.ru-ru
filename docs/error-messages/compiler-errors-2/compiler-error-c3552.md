---
title: Ошибка компилятора C3552 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd9f7ae37500e115fa33fa61298cab800c88f9c7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081264"
---
# <a name="compiler-error-c3552"></a>Ошибка компилятора C3552

"имя_типа": тип возвращаемого значения с поздним заданием не может содержать "auto"

Если вы используете ключевое слово `auto` для типа возвращаемого значения функции, необходимо использовать тип возвращаемого значения с поздним заданием. Однако нельзя использовать другое ключевое слово `auto` для указания типа возвращаемого значения с поздним заданием. Например, представленный ниже фрагмент кода приводит к возникновению ошибки C3552.

`auto myFunction->auto; // C3552`
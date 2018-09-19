---
title: Неустранимая ошибка C1126 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f014aafc60a36bfbb4edad50e7e3ceede6e3c8b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062479"
---
# <a name="fatal-error-c1126"></a>Неустранимая ошибка C1126

«Идентификатор»: автоматическое выделение памяти превышает размер

Пространство, выделенное для локальных переменных функции (а также ограниченное пространство, используемое компилятором, такие как дополнительные 20 б для изменяемых функций) превышает предел.

Чтобы исправить эту ошибку, используйте `malloc` или `new` выделить большие объемы данных.
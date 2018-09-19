---
title: Предупреждение программы NMAKE U4011 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1038ee86f76789451565ab6799795c851c95a95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118340"
---
# <a name="nmake-warning-u4011"></a>Предупреждение программы NMAKE U4011

'target': не все зависимые компоненты; целевой объект не построен

Зависимый компонент заданного целевого объекта не существует или устарела, и команда обновления возвратила ненулевой код выхода. Параметр /K дал NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.

Это предупреждение предшествует предупреждение [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) для каждой зависимости, которую не удалось создать или обновить.
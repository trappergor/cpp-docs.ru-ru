---
title: Предупреждение программы NMAKE U4011
ms.date: 11/04/2016
f1_keywords:
- U4011
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
ms.openlocfilehash: 6b1701ffc83f849d2482bd14b25d65c04c496899
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193151"
---
# <a name="nmake-warning-u4011"></a>Предупреждение программы NMAKE U4011

' target ': доступны не все зависимые объекты; Целевой объект не построен

Зависимая от данного целевого объекта либо не существует, либо устарела, а команда для обновления зависимого кода вернула ненулевой код выхода. Параметр/K сообщает NMAKE, чтобы продолжить обработку несвязанных частей сборки и выдать код выхода 1 после завершения сеанса NMAKE.

Этому предупреждению предшествует предупреждение [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) для каждого зависимого, которое не удалось создать или обновить.

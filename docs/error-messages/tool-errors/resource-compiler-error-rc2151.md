---
title: Ошибка компилятора ресурсов RC2151
ms.date: 11/04/2016
f1_keywords:
- RC2151
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
ms.openlocfilehash: 8eaa50bc6080e37a4a74585eb03cbe4e40893bce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598891"
---
# <a name="resource-compiler-error-rc2151"></a>Ошибка компилятора ресурсов RC2151

Невозможно повторно использовать строковые константы

Вы используете то же значение дважды в **STRINGTABLE** инструкции. Убедитесь, что не смешана перекрывающиеся десятичные и шестнадцатеричные значения.

Каждый идентификатор в **STRINGTABLE** должно быть уникальным. Для достижения максимальной эффективности используйте зависимые константы, которые начинаются на кратен 16.
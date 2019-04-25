---
title: Ошибка компилятора ресурсов RC2151
ms.date: 11/04/2016
f1_keywords:
- RC2151
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
ms.openlocfilehash: 8eaa50bc6080e37a4a74585eb03cbe4e40893bce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173448"
---
# <a name="resource-compiler-error-rc2151"></a>Ошибка компилятора ресурсов RC2151

Невозможно повторно использовать строковые константы

Вы используете то же значение дважды в **STRINGTABLE** инструкции. Убедитесь, что не смешана перекрывающиеся десятичные и шестнадцатеричные значения.

Каждый идентификатор в **STRINGTABLE** должно быть уникальным. Для достижения максимальной эффективности используйте зависимые константы, которые начинаются на кратен 16.
---
title: Ошибка компилятора ресурсов RC2151
ms.date: 11/04/2016
f1_keywords:
- RC2151
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
ms.openlocfilehash: 9d4eea92321ca8373f3ad5f121f4a8e96d878e79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191266"
---
# <a name="resource-compiler-error-rc2151"></a>Ошибка компилятора ресурсов RC2151

невозможно повторно использовать строковые константы

Одно и то же значение используется дважды в операторе **STRINGTABLE** . Убедитесь, что вы не смешиваете перекрывающиеся десятичные и шестнадцатеричные значения.

Каждый идентификатор в **STRINGTABLE** должен быть уникальным. Для максимальной эффективности используйте смежные константы, которые начинаются с кратного 16.

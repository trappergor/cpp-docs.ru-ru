---
title: Предупреждение программы NMAKE U4004 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a89bb8abf212c8a0ffa9fb40fe5d3ea43307a08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016654"
---
# <a name="nmake-warning-u4004"></a>Предупреждение программы NMAKE U4004

слишком много правил для целевой объект «targetname»

Был указан более одного блока описания для заданного целевого объекта с помощью одного двоеточия (**:**) в качестве разделителей. NMAKE выполнения команды в первом блоке описание и не последующих блоков.

Чтобы указать тот же целевой объект в несколько зависимостей, используйте двойные двоеточия (`::`) в качестве разделителя в каждой строке зависимость.
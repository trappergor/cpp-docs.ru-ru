---
title: Ошибка средств компоновщика LNK2008
ms.date: 11/04/2016
f1_keywords:
- LNK2008
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
ms.openlocfilehash: 97bb2be18da5d166d1d5fba42e4ec8ce1f0439fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544226"
---
# <a name="linker-tools-error-lnk2008"></a>Ошибка средств компоновщика LNK2008

Целевой объект адресной привязки не выравнивается 'symbol_name'

Целевой объект адресной привязки найти ССЫЛКУ в объектном файле, который был не были правильно выровнены.

Эта ошибка может быть вызвана выравниванием пользовательского (например, #pragma [пакет](../../preprocessor/pack.md)), [выровнять](../../cpp/align-cpp.md) модификатор, или с помощью кода языка ассемблера, которая изменяет выравниванием.

Если код не использует перечисленные выше, это может быть вызвано компилятор.
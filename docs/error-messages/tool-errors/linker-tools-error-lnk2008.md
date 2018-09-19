---
title: Ошибка средств компоновщика LNK2008 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2008
dev_langs:
- C++
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18eda06e7f133ada4de1b7ec28ac21be205a71f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086815"
---
# <a name="linker-tools-error-lnk2008"></a>Ошибка средств компоновщика LNK2008

Целевой объект адресной привязки не выравнивается 'symbol_name'

Целевой объект адресной привязки найти ССЫЛКУ в объектном файле, который был не были правильно выровнены.

Эта ошибка может быть вызвана выравниванием пользовательского (например, #pragma [пакет](../../preprocessor/pack.md)), [выровнять](../../cpp/align-cpp.md) модификатор, или с помощью кода языка ассемблера, которая изменяет выравниванием.

Если код не использует перечисленные выше, это может быть вызвано компилятор.
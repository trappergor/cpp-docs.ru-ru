---
title: Предупреждение компилятора ресурсов RC4005 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 589fd008b3927887a8144b2fc63d2cbbde2af913
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028523"
---
# <a name="resource-compiler-warning-rc4005"></a>Предупреждение компилятора ресурсов RC4005

«Идентификатор»: макроопределения

Идентификатор определен дважды. Компилятор использовал второе определение макроса.

Это предупреждение может быть вызвано определение макроса в командной строке и в коде с `#define` директива. Она также может быть вызвана макросы, импортированные из включаемых файлов.

Чтобы устранить предупреждение, удалите одно из определений или используйте `#undef` директиву перед вторым определением.
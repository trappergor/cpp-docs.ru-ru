---
title: Предупреждение средств компоновщика LNK4022 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 644e7a9ba26dab15e2bfa2a269f62c04f0510180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041003"
---
# <a name="linker-tools-warning-lnk4022"></a>Предупреждение средств компоновщика LNK4022

не удается найти уникальное соответствие для символа «символ»

ССЫЛКА или LIB обнаружено несколько соответствует для упрощенного заданного символа и не может разрешить неоднозначность. Создается выходной файл не (.exe, .dll, .exp или .lib). Это предупреждение сопровождается одно предупреждение [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) для каждого Дублировать символ после чего возникает неустранимая ошибка [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).

Чтобы устранить это предупреждение, укажите символ в декорированном виде. Запустите [DUMPBIN](../../build/reference/dumpbin-options.md) на объект для просмотра внутренних имен.
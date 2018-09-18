---
title: Соответствие C стандарту ANSI | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- Ansi
dev_langs:
- C++
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5fceb2681befa5ed9c8c82facb85442aed2d646
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023349"
---
# <a name="ansi-c-compliance"></a>Совместимость ANSI с C

Соглашение об именовании для всех относящихся к системам Microsoft идентификаторов в системе времени выполнения (например, функций, макросов, констант, переменных и определений типов) соответствует стандарту ANSI. В этой документации любая функция времени выполнения, которая соответствует стандартам ANSI/ISO C, помечена как ANSI-совместимая. ANSI-совместимые приложения должны использовать только эти функции, соответствующие стандарту ANSI.

Имена функций и глобальных переменных, которые относятся к системам Microsoft, начинаются с одного символа подчеркивания. Эти имена можно переопределять только локально, в области действия своего кода. Например, при включении файлов заголовков времени выполнения Microsoft можно локально переопределить функцию для систем Microsoft с именем `_open`, объявив локальную переменную с таким же именем. Однако нельзя использовать это имя для собственных глобальных функций или глобальных переменных.

Имена относящихся к системам Microsoft макросов и констант манифеста начинаются с двух символов подчеркивания или с одного ведущего символа подчеркивания с идущей за ним прописной буквой. Область видимости этих идентификаторов абсолютна. Например, по этой причине вы не можете использовать идентификатор **_UPPER**, используемый исключительно в системах корпорации Майкрософт.

## <a name="see-also"></a>См. также

[Совместимость](../c-runtime-library/compatibility.md)
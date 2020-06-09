---
title: Переопределение стандартной маршрутизации команд
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
ms.openlocfilehash: 680b185f8d68a834862bc0fe14bf6e7984effd65
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617726"
---
# <a name="overriding-the-standard-command-routing"></a>Переопределение стандартной маршрутизации команд

В редких случаях, когда необходимо реализовать некоторую разновидность маршрутизации стандартной платформы, ее можно переопределить. Идея состоит в том, чтобы изменить маршрутизацию в одном или нескольких классах путем переопределения `OnCmdMsg` в этих классах. Сделайте следующее:

- В классе, который прерывает порядок передачи объекту, не заданному по умолчанию.

- В новом объекте, не используемом по умолчанию, или в целевой команде он может передаваться командам.

Если в маршрутизацию вставляется какой-либо новый объект, его класс должен быть классом целевого объекта. При переопределении версий убедитесь, что `OnCmdMsg` вызывается переопределяемая версия. Примеры см. в описании функции члена [OnCmdMsg](reference/ccmdtarget-class.md#oncmdmsg) класса `CCmdTarget` в *справочнике MFC* и версиях в таких классах, как `CView` и `CDocument` в приведенном исходном коде.

## <a name="see-also"></a>См. также раздел

[Вызовы обработчика со стороны платформы](how-the-framework-calls-a-handler.md)

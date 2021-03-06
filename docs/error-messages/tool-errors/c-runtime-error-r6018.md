---
title: Ошибка времени выполнения C R6018
ms.date: 11/04/2016
f1_keywords:
- R6018
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
ms.openlocfilehash: 83ad191fe1518e5e6bab0798840415ef392db71e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197292"
---
# <a name="c-runtime-error-r6018"></a>Ошибка времени выполнения C R6018

Непредвиденная ошибка кучи

> [!NOTE]
> Если при запуске приложения возникло это сообщение об ошибке, работа приложения была завершена из-за внутренней проблемы. Существует несколько возможных причин возникновения этой ошибки, но часто это вызвано дефектом в коде приложения.
>
> Для устранения этой ошибки попробуйте выполнить следующие действия:
>
> - Используйте страницу **приложения и компоненты** или **программы и компоненты** на **панели управления** , чтобы восстановить или переустановить программу.
> - Проверьте **Центр обновления Windows** на **панели управления** для обновлений программного обеспечения.
> - Проверьте наличие обновленной версии приложения. Если проблема не исчезнет, обратитесь к поставщику приложения.

**Сведения для программистов**

Программа обнаружила непредвиденную ошибку при выполнении операции управления памятью.

Эта ошибка обычно возникает, если программа случайно изменяет данные кучи времени выполнения. Однако это также может быть вызвано внутренней ошибкой в среде выполнения или коде операционной системы.

Чтобы устранить эту проблему, проверьте наличие ошибок повреждения кучи в коде. Дополнительные сведения и примеры см. в разделе [сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Затем убедитесь, что вы используете новейшие распространяемые компоненты для развертывания приложения. Дополнительные сведения см. [в разделе Развертывание C++в Visual ](../../windows/deployment-in-visual-cpp.md).

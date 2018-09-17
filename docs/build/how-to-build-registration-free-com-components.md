---
title: 'Практическое: построение без регистрации COM-компонентов | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0a9e1769ff0ba9a0589f9d59c3d1f1ed2fc5bcb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699859"
---
# <a name="how-to-build-registration-free-com-components"></a>Практическое руководство. Сборка не требующих регистрации компонентов COM

Без регистрации COM-компонентами являются компоненты COM, содержащие манифесты, встроенные в библиотеки DLL.

### <a name="to-build-manifests-into-com-components"></a>Для создания манифестов в COM-компонентов

1. Откройте страницы свойств проекта для COM-компонента.

1. Разверните **свойства конфигурации** узел, а затем разверните **инструмент манифеста** узла.

1. Выберите **входные и выходные данные** страницу свойств, а затем задайте **внедренный манифест** равным **Да**.

1. Нажмите кнопку **ОК**.

1. Постройте решение.

## <a name="see-also"></a>См. также

[Изолированные приложения](/windows/desktop/SbsCs/isolated-applications)<br/>
[О сборках Side-by-Side](/windows/desktop/SbsCs/about-side-by-side-assemblies-)<br/>
[Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](../build/how-to-build-isolated-applications-to-consume-com-components.md)
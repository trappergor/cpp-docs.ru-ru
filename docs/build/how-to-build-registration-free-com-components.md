---
title: Практическое руководство. Сборка не требующих регистрации компонентов COM
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 4f4ebf121b761c37969fa3f9788bda52d913f340
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463535"
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
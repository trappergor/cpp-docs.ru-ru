---
title: Практическое руководство. Построение компонентов COM без регистрации
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 503c3e4399359d793ce660f36844d2edc6602146
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416778"
---
# <a name="how-to-build-registration-free-com-components"></a>Практическое руководство. Построение компонентов COM без регистрации

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

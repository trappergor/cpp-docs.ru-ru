---
title: Практическое руководство. Построение компонентов COM без регистрации
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 783677c97835acc98751fc4a19f9405af752b71a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809604"
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

[Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](how-to-build-isolated-applications-to-consume-com-components.md)

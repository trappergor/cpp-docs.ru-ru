---
title: Практическое руководство. Сборка не требующих регистрации компонентов COM
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: 783677c97835acc98751fc4a19f9405af752b71a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188942"
---
# <a name="how-to-build-registration-free-com-components"></a>Практическое руководство. Сборка не требующих регистрации компонентов COM

Не требующие регистрации компоненты COM — это компоненты COM, манифесты которых встроены в библиотеки DLL.

### <a name="to-build-manifests-into-com-components"></a>Встраивание манифестов в компоненты COM

1. Откройте страницы свойств проекта для компонента COM.

1. Разверните узлы **Свойства конфигурации** и **Инструмент манифеста**.

1. Выберите страницу свойств **Вход и выход** и задайте для свойства **Внедренный манифест** значение **Да**.

1. Нажмите кнопку **ОК**.

1. Постройте решение.

## <a name="see-also"></a>См. также

[Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](how-to-build-isolated-applications-to-consume-com-components.md)

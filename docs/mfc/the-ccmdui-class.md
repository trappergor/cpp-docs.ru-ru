---
title: Класс CCmdUI
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 105aa7ad6c5cc6a5563dbde8145327a2b3d066a1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447139"
---
# <a name="the-ccmdui-class"></a>Класс CCmdUI

Когда команда обновления передается в свой обработчик, платформа передает обработчику указатель на объект `CCmdUI` (или на объект класса, производного от `CCmdUI`). Этот объект представляет элемент меню или кнопку панели инструментов или другой объект пользовательского интерфейса, создавший команду. Обработчик обновлений вызывает функции-члены структуры `CCmdUI` с помощью указателя, чтобы обновить объект пользовательского интерфейса. Например, Вот обработчик обновления для пункта меню Очистить все:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Этот обработчик вызывает `Enable` функцию члена объекта с доступом к элементу меню. `Enable` делает элемент доступным для использования.

## <a name="see-also"></a>См. также раздел

[Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)

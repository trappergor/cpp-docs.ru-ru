---
title: Класс CCmdUI
ms.date: 11/04/2016
f1_keywords:
- CCmdUI
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 47ef359f71d9dd30f2ba1ff1c4cf504bccd33ffd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667952"
---
# <a name="the-ccmdui-class"></a>Класс CCmdUI

Когда он направляет его обработчик команды update, платформа передает обработчик указатель на `CCmdUI` объекта (или на объект `CCmdUI`-производного класса). Этот объект представляет меню или панели инструментов кнопки или другого объекта пользовательского интерфейса, вызвавшего команду. Обработчик обновлений вызывает член функции `CCmdUI` структуры через указатель для обновления пользовательского интерфейса объекта. Например вот обработчик для элемента меню очистить все:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Этот обработчик вызывает `Enable` функция-член объекта, имеющего доступ к пункту меню. `Enable` делает элемент доступным для использования.

## <a name="see-also"></a>См. также

[Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)


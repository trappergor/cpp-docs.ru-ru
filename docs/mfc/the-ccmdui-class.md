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
ms.openlocfilehash: 8e0af0703924d6fae626d3753b8523efe0c56652
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306305"
---
# <a name="the-ccmdui-class"></a>Класс CCmdUI

Когда он направляет его обработчик команды update, платформа передает обработчик указатель на `CCmdUI` объекта (или на объект `CCmdUI`-производного класса). Этот объект представляет меню или панели инструментов кнопки или другого объекта пользовательского интерфейса, вызвавшего команду. Обработчик обновлений вызывает член функции `CCmdUI` структуры через указатель для обновления пользовательского интерфейса объекта. Например вот обработчик для элемента меню очистить все:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Этот обработчик вызывает `Enable` функция-член объекта, имеющего доступ к пункту меню. `Enable` делает элемент доступным для использования.

## <a name="see-also"></a>См. также

[Практическое руководство. Обновление объектов пользовательского интерфейса](../mfc/how-to-update-user-interface-objects.md)

---
title: Класс CCmdUI | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18b5675aff2d10f224238a1ba6d3b919e1b285a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374586"
---
# <a name="the-ccmdui-class"></a>Класс CCmdUI

Когда он направляет его обработчик команды update, платформа передает обработчик указатель на `CCmdUI` объекта (или на объект `CCmdUI`-производного класса). Этот объект представляет меню или панели инструментов кнопки или другого объекта пользовательского интерфейса, вызвавшего команду. Обработчик обновлений вызывает член функции `CCmdUI` структуры через указатель для обновления пользовательского интерфейса объекта. Например вот обработчик для элемента меню очистить все:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Этот обработчик вызывает `Enable` функция-член объекта, имеющего доступ к пункту меню. `Enable` делает элемент доступным для использования.

## <a name="see-also"></a>См. также

[Практическое руководство. Обновление объектов интерфейса пользователя](../mfc/how-to-update-user-interface-objects.md)


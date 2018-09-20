---
title: Настройка для MFC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- customizations, MFC Extensions
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 640d6726623e8fb6d563153823f449f7caefcf30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385005"
---
# <a name="customization-for-mfc"></a>Настройка для MFC

В этом разделе приведены советы по настройке приложения MFC.

## <a name="general-customizations"></a>Общие настройки

Можно сохранить и загрузить состояние приложения в реестр. Если включить этот параметр, ваше приложение загрузит исходное состояние из реестра. Если изменить исходный макет закрепления для вашего приложения, необходимо очистить данные реестра для вашего приложения. В противном случае данные в реестре переопределит все изменения, внесенные в исходный макет.

## <a name="class-specific-customizations"></a>Класс специальных настроек

Дополнительные настройки советы можно найти в следующих разделах:

- [Класс CBasePane](../mfc/reference/cbasepane-class.md)

- [Класс CDockablePane](../mfc/reference/cdockablepane-class.md)

- [Класс CDockingManager](../mfc/reference/cdockingmanager-class.md)

- [Класс CMFCBaseTabCtrl](../mfc/reference/cmfcbasetabctrl-class.md)

## <a name="additional-customization-tips"></a>Советы по дополнительной настройке

[Настройка мыши и клавиатуры](../mfc/keyboard-and-mouse-customization.md)

[Инструменты, определяемые пользователем](../mfc/user-defined-tools.md)

## <a name="see-also"></a>См. также

[Приложения MFC для рабочего стола](../mfc/mfc-desktop-applications.md)<br/>
[Вопросы безопасности во время настройки](../mfc/security-implications-of-customization.md)


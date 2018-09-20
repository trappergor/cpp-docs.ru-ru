---
title: Добавление класса MFC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.adding.mfc
dev_langs:
- C++
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes
ms.assetid: 9a96b67f-40bf-43d4-8872-2f8dfc5404f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86e42ab5c2e8e15f5f56687b5ca99d160270017b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436368"
---
# <a name="adding-an-mfc-class"></a>Добавление класса MFC

Чтобы добавить классы, производные от классов библиотеки Microsoft Foundation Class (MFC) в проект, используйте **Добавление класса** команд, доступных из [представление классов](/visualstudio/ide/viewing-the-structure-of-code). Укажите имя нового класса, выберите базовый класс и выберите идентификатор диалоговое окно, с которым он связан (если таковые имеются). Мастера кода создает файл заголовка и файл реализации и добавляет их в проект.

> [!NOTE]
>  Классы MFC можно добавить к приложению ATL COM, если вы изначально [создано приложение с поддержкой MFC](../../atl/reference/mfc-support-in-atl-projects.md). Классы MFC можно также добавить в проекты Win32 с поддержкой MFC.

### <a name="to-add-an-mfc-class-to-your-project"></a>Добавление класса MFC в проект

1. Из представления классов щелкните правой кнопкой мыши имя проекта. Нажмите кнопку **добавить** и нажмите кнопку **Добавление класса** открыть [Добавление класса](../../ide/add-class-dialog-box.md) диалоговое окно.

1. В области «Шаблоны» выберите **класс MFC** и нажмите клавишу **добавить** кнопки.

1. Определите параметры для нового класса в [мастер классов MFC](../../mfc/reference/mfc-add-class-wizard.md) диалоговое окно.

1. Нажмите кнопку **Готово** закрыть мастер и увидеть новый класс в класс. Можно также просмотреть файлы, созданные с помощью мастера в **обозревателе решений**.

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Общие сведения о классе](../../mfc/class-library-overview.md)


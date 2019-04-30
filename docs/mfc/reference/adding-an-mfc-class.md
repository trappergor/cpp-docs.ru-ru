---
title: Добавление класса MFC
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.adding.mfc
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes
ms.assetid: 9a96b67f-40bf-43d4-8872-2f8dfc5404f1
ms.openlocfilehash: 1cc3dc734917da46af99e67da40fe243941102e3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296778"
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

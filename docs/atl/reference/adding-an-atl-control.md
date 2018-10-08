---
title: Добавление элемента управления ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a996df63430a2d6b1942112122a1f185ba8f13de
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48859605"
---
# <a name="adding-an-atl-control"></a>Добавление элемента управления ATL

Этот мастер используется для добавления объекта пользовательского интерфейса в проект, который поддерживает интерфейсы для всех потенциальных контейнеров. Для поддержки этих интерфейсов, проект должен быть создан как приложение ATL или как приложение MFC с поддержкой ATL. Вы можете использовать [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md), чтобы создать приложение ATL, или [добавить объект ATL в свое приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), чтобы реализовать поддержку ATL для приложения MFC.

## <a name="to-add-an-atl-control-to-your-project"></a>Добавление элемента управления ATL в проект

1. В любом **обозревателе решений** или [представление классов](/visualstudio/ide/viewing-the-structure-of-code), щелкните правой кнопкой мыши имя проекта, к которому вы хотите добавить простой объект ATL.

1. Нажмите кнопку **добавить** из контекстного меню и нажмите кнопку **Добавление класса**.

1. В [Добавление класса](../../ide/add-class-dialog-box.md) диалоговом окне в области «Шаблоны» щелкните **управления ATL**, а затем нажмите кнопку **добавить** для отображения [мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md).

С помощью **мастер элементов управления ATL**, можно создать один из трех типов элементов управления:

- Стандартный элемент управления

- Составной элемент управления

- Элемент управления DHTML

Кроме того, можно уменьшить размер элемента управления и удалить интерфейсы, не используемые большинством контейнеров, выбрав **минимальный элемент управления** на **параметры** странице мастера.

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей в составной элемент управления](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)   

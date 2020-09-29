---
title: Добавление объектов и элементов управления в проект ATL
ms.date: 05/09/2019
f1_keywords:
- vc.appwiz.ATL.controls
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
ms.openlocfilehash: 6acd60d430f13906d11e9a9b3e7c5655ee94badb
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499299"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Добавление объектов и элементов управления в проект ATL

> [!NOTE]
> Мастер компонентов ATL COM+ 1.0, мастер объекта-получателя ATL OLE DB и мастер компонентов ASP ATL недоступны в Visual Studio 2019 и более поздних версий.

Вы можете использовать один из мастеров кода ATL, чтобы добавить объект или элемент управления в проекты на основе ATL или MFC. Для каждого COM-объекта или элемента управления, который вы добавляете, мастер создает файлы CPP и H, а также RGS-файл для поддержки реестра на основе скрипта. Следующие мастера кода ATL доступны в Visual Studio.

- [Простой объект ATL](../../atl/reference/atl-simple-object-wizard.md)
- [Диалог ATL](../../atl/reference/atl-dialog-wizard.md)
- [Элемент управления ATL](../../atl/reference/atl-control-wizard.md)
- [Свойства ATL](../../atl/reference/atl-property-page-wizard.md)
- [ASP-компонент библиотеки ATL](../../atl/reference/atl-active-server-page-component-wizard.md)
- [Adding an ATL OLE DB Consumer](../../atl/reference/atl-ole-db-consumer-wizard.md) (Добавление объекта-получателя ATL OLE DB)
- [Добавление в MFC поддержки ATL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)
- [Мастер компонентов ATL COM+ 1.0](../../atl/reference/atl-com-plus-1-0-component-wizard.md)
- [Поставщик ATL OLE DB](../../atl/reference/atl-ole-db-provider-wizard.md)

> [!NOTE]
> Прежде чем добавить объект ATL в проект, изучите сведения и требования для объекта в соответствующих разделах справки.

## <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>Добавление объекта или элемента управления с помощью мастера управления ATL

1. Щелкните правой кнопкой мыши узел проекта в **обозревателе решений** и выберите в контекстном меню пункт **Добавить**. Нажмите **Добавить класс**.

   Откроется диалоговое окно [Добавление класса](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box).

1. Выберите папку **ATL** на панели **Категории** и выберите объект для вставки на панели **Шаблоны**. Нажмите кнопку **Открыть**. Откроется мастер кода для выбранного объекта.

   > [!NOTE]
   > Если вы хотите добавить объект ATL в проект MFC, необходимо добавить поддержку ATL в существующий проект. Это можно сделать, следуя инструкциям в разделе [Добавление поддержки ATL в проект MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).

   Кроме того, если вы пытаетесь добавить объект ATL в проект MFC, не добавив предварительно поддержку ATL, Visual Studio предложит указать, хотите ли вы добавить поддержку ATL в проект. Нажмите **Да**, чтобы добавить поддержку ATL в проект, и откройте выбранный мастер ATL.

## <a name="see-also"></a>См. также раздел

[Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Типы проектов C++ в Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Программирование с помощью ATL и кода времени выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

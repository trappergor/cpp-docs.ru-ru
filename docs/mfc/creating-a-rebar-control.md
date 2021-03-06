---
title: Создание элемента управления главной панели
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
ms.openlocfilehash: 6828fa3b47eaa1e29579b09611d85cd68702c332
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617128"
---
# <a name="creating-a-rebar-control"></a>Создание элемента управления главной панели

Объекты [CReBarCtrl](reference/crebarctrl-class.md) должны быть созданы до того, как родительский объект станет видимым. Это позволяет избежать проблем с вырисовкой.

Например, элементы управления главной панели (используемые в окне объектов фрейма) обычно используются в качестве родительских окон для элементов управления ToolBar. Таким образом, родительским элементом управления главной панели является объект окна фрейма. Так как объект окна фрейма является родительским, `OnCreate` функция-член (родителя) является отличным местом для создания элемента управления "Главная панель".

Для использования `CReBarCtrl` объекта, как правило, выполняются следующие действия.

### <a name="to-use-a-crebarctrl-object"></a>Использование объекта CReBarCtrl

1. Создайте объект [CReBarCtrl](reference/crebarctrl-class.md) .

1. Вызовите [CREATE](reference/crebarctrl-class.md#create) , чтобы создать общий элемент управления "Главная панель Windows" и присоединить его к `CReBarCtrl` объекту, указав все нужные стили.

1. Загрузите точечный рисунок с вызовом [CBitmap:: лоадбитмап](reference/cbitmap-class.md#loadbitmap), который будет использоваться в качестве фона для объекта элемента управления "Главная панель".

1. Создание и инициализация любых дочерних объектов окна (панелей инструментов, элементов управления диалогового окна и т. д.), которые будут содержаться в объекте элемента управления "Главная панель".

1. Инициализируйте структуру **ребарбандинфо** с необходимыми сведениями для вставляемого диапазона.

1. Вызовите [инсертбанд](reference/crebarctrl-class.md#insertband) , чтобы вставить существующие дочерние окна (например, `m_wndReToolBar` ) в новый элемент управления главной панели. Дополнительные сведения о вставке полос в существующий элемент управления главной панели см. в разделе [элементы управления главной панели и полосы](rebar-controls-and-bands.md).

## <a name="see-also"></a>См. также раздел

[Использование CReBarCtrl](using-crebarctrl.md)<br/>
[Элементы управления](controls-mfc.md)

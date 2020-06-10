---
title: Установка связи с древовидным элементом управления
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: f480cdad2fce53f830b8067083a8a4be4b4e4848
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619646"
---
# <a name="communicating-with-a-tree-control"></a>Установка связи с древовидным элементом управления

Для вызова функций-членов в объекте [CTreeCtrl](reference/ctreectrl-class.md) используются различные методы в зависимости от способа создания объекта.

- Если элемент управления "дерево" находится в диалоговом окне, используйте переменную-член типа `CTreeCtrl` , созданную в классе диалогового окна.

- Если элемент управления "дерево" является дочерним окном, используйте `CTreeCtrl` объект (или указатель), который использовался для создания объекта.

- Если вы используете `CTreeView` объект, используйте функцию [CTreeView:: GetTreeCtrl](reference/ctreeview-class.md#gettreectrl) , чтобы получить ссылку на элемент управления "дерево". Можно инициализировать другую ссылку с этим значением или назначить адрес ссылки на `CTreeCtrl` указатель.

## <a name="see-also"></a>См. также раздел

[Использование CTreeCtrl](using-ctreectrl.md)<br/>
[Элементы управления](controls-mfc.md)
